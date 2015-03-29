# 连接到历史数据库

**ovirt_engine_history** 数据库位于在安装 oVirt 企业级虚拟化管理中心时创建的 PostgreSQL 数据库中。

要想本地连接到数据库，您需要使用一个与 PostgreSQL 兼容的查询工具。

**概述**

历史数据仓库还可以通过远程访问。您需要修改的所有 PostgresSQL 配置文件都在 **/var/lib/pgsql/data** 中。

**允许远程访问历史数据库**

1. 编辑 **postgresql.conf** 文件，添加以下两个参数。
```
ssl=on
listen_addresses = "*"
```
如果只运行特定的主机访问数据库，您需要写以逗号分隔的 IP 地址列表或主机名列表，而不是写 "*"。
2. 编辑 **pg_hba.conf**，添加以下内容：

```
hostssl     all    all     <net address/mask>      md5
```
其中 &lt;net address/mask&gt; 是允许访问数据库的主机的 IP 地址和子网掩码；例如，192.168.0.0/24。

3. 为下面的证书和密钥创建软链接，以便 PostgreSQL 找到它们：

```
# ln -s /etc/pki/ovirt-engine/certs/engine.cer /var/lib/pgsql/data/server.crt
# ln -s /etc/pki/ovirt-engine/keys/engine_id_rsa /var/lib/pgsql/data/server.key
```
这个证书和密钥是在安装 oVirt 企业级虚拟化管理中心时被创建出来的。然而 PostgresSQL 需要将它们放在一个特殊的位置(**/var/lib/pgsql/data/**)，文件名为(**server.crt** 和 **server.key**)。

另外，您还可以使用[PostgreSQL Manual](http://www.postgresql.org/docs/8.4/static/ssl-tcp.html#SSL-FILE-USAGE)文档中介绍的命令来创建新的证书和密钥文件。
4. 停止 engine 服务：


 ```
# service ovirt-engine stop
```
5. 重新启动 PostgreSQL 服务：


 ```
# service postgresql restart
```
6. 删除并部署 Jasper WAR 文件：

   a. 删除 **.deployed** 文件：
   ```
   # rm /var/lib/ovirt-engine/deployments/rhevm-reports.war.deployed
   ```
   它创建一个 **.undeployed** 文件：

   **/var/lib/ovirt-engine/deployments/rhevm-reports.war.undeployed** 如果存在 **.undeployed** 文件，这个应用程序就会停止。

   b. 删除 **.undeployed** 文件：
   ```
   # rm /var/lib/ovirt-engine/deployments/rhevm-reports.war.undeployed
   ```

   c. 部署 WAR 文件：
   ```
   # touch /var/lib/ovirt-engine/deployments/rhevm-reports.war.dodeploy
   ```
   它会创建一个 **.deployed** 文件：
   **/var/lib/ovirt-engine/deployments/rhevm-reports.war.deployed**
7. 添加一个 **iptables** 规则以允许外部机器连接到 oVirt 虚拟化管理中心并访问 PostgreSQL。例如，在一个默认的 **iptables** 配置中，运行以下命令在 SSH 规则后面添加一个新规则：

```
iptables -I INPUT 5 -p tcp -m state --state NEW --dport 5432 -j ACCEPT
```
8. 启动 engine 服务。

```
# service ovirt-engine start
```
**结果**

您已经可以让一个拥有证书的远程用户访问 oVirt 企业级虚拟化历史数据库。

