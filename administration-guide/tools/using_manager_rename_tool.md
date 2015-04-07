# 使用oVirt 企业级虚拟化管理中心重命名工具
**概述**

使用 **ovirt-engine-rename** 命令更新 oVirt 企业级虚拟化管理中心 的 FQDN 域名记录。

**使用 oVirt 企业级虚拟化管理中心重命名工具**

1. 在 DNS 系统中准备好 Manager 新的 FQDN 域名记录以及其他相关记录。

1. 如果使用 DHCP，修改 DHCP 配置。

1. 修改 Manager 服务器的主机名。

1. 执行下面的命令：

 ```
 # /usr/share/ovirt-engine/setup/bin/ovirt-engine-rename
 ```

1. 出现下面的提示时，按下**回车键**，关闭 Manager：

 ```
 During execution engine service will be stopped (OK, Cancel)   [OK]:
 ```

1. 出现下面的提示时，输入新的 FQDN 域名：

 ```
New fully qualified server name:[new name]
```

> **注意**
>
> **ovirt-engine-rename** 支持--name参数，参数后面直接指定Manager新的fqdn域名，可以省去后面提示输入域名的步骤，如：
> `# /usr/share/ovirt-engine/setup/bin/ovirt-engine-rename --name=[new name]`

 **结果**

  **ovirt-engine-rename** 命令更新了 Manager 的 FQDN 域名记录。

