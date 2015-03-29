# 控制台连接协议介绍

连接协议是虚拟机提供提供图形界面的访问方式给用户，让用户方便地使用虚拟机，就像在用户使用一台物理的机器一样的体验。oVirt
虚拟化管理平台目前提供如下三种连接协议：

**SPICE**
Simple Protocol for Independent Computing Environments（SPICE）是 Linux 虚拟机与 Windows
虚拟机建议的连接协议。SPICE 被安装在连接虚拟机控制台的客户机器上。

**VNC**
Virtual Network Computing（VNC）是 Linux 虚拟机与 Windows 虚拟机的连接协议。SPICE 被安装在连接虚拟机控制台的客户机器上。

**RDP**
Remote Desktop Protocol（RDP）只能用于 Windows 虚拟机的连接协议。而且必须要在一台 Windows
虚拟机上且安装了 RDP 的客户客户端机器去连接。更多的是，你还需要在虚拟机上面设置 RDP
服务端并且允许防火墙不拦截 RDP 的请求才能连接。


> **注意**
>
> 目前 SPICE 不在 Windows8 虚拟机上面支持。如果一台 Windows8 上配置了 SPICE
> 显示协议，系统将会检测没有 SPICE 驱动并且自动地回退到 RDP 协议。
