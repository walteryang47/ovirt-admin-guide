# 虚拟化宿主机防火墙要求

oVirt虚拟化宿主机 和 CentOS 7
主机都要求系统防火墙开放一系列的端口以允许网络流量通过。使用 oVirt虚拟化宿主机
的情况下防火墙规则将会自动被配置。对于使用 CentOS 7
主机的情况，则需要手动对防火墙进行配置。

**虚拟化宿主机防火墙要求**

|端口|协议|源机器|目标机器|目的|
|----|----|------|--------|----|
|22|TCP|youerelouaioVirt虚拟化管理中心splashleesplashyou|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|SSH 连接|
|5900 - 6411|TCP|youerelouai管理员门户客户端splashleeelouai用户门户客户端splashleesplashyou|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|通过 VNC 和 spice 的远程客户控制台访问。这些端口必须打开，客户端才能够连接至虚拟机。|
|5989|TCP|youerelouai通用信息模型对象管理器（CIMOM）splashleesplashyou|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|被通用信息模型对象管理器（CIMOM）使用以监控运行在该虚拟化宿主机上的虚拟机的状态。如果您希望在您的虚拟化环境中使用 CIMOM 来监控虚拟机状态，必须确保打开此端口。|
|16514|TCP|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|使用 *libvirt* 进行的虚拟机迁移。|
|49152 - 49216|TCP|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|使用 VDSM 进行的虚拟机迁移和隔离。这些端口必须被打开，才能够进行自动以及手动开始的虚拟机迁移。|
|54321|TCP|youerelouaioVirt虚拟化管理中心splashleeelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|youerelouaioVirt虚拟化宿主机splashleeelouai其他虚拟化宿主机splashleesplashyou|与oVirt虚拟化管理中心和其它虚拟化宿主机之间的进行的 VDSM 通信。|

推荐的（默认）值：由 vdsm 初始化脚本自动生成

    *filter
    :INPUT ACCEPT [0:0]
    :FORWARD ACCEPT [0:0]
    :OUTPUT ACCEPT [0:0]
    -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
    -A INPUT -p icmp -j ACCEPT
    -A INPUT -i lo -j ACCEPT
    # vdsm
    -A INPUT -p tcp --dport 54321 -j ACCEPT
    # libvirt tls
    -A INPUT -p tcp --dport 16514 -j ACCEPT
    # SSH
    -A INPUT -p tcp --dport 22 -j ACCEPT
    # guest consoles
    -A INPUT -p tcp -m multiport --dports 5634:6166 -j ACCEPT
    # migration
    -A INPUT -p tcp -m multiport --dports 49152:49216 -j ACCEPT
    # snmp
    -A INPUT -p udp --dport 161 -j ACCEPT
    # Reject any other input traffic
    -A INPUT -j REJECT --reject-with icmp-host-prohibited
    -A FORWARD -m physdev ! --physdev-is-bridged -j REJECT --reject-with icmp-host-prohibited
    COMMIT


