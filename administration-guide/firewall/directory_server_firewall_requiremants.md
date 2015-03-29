# 目录服务器防火墙要求

oVirt虚拟化管理中心需要目录服务器以进行用户验证。在该目录服务器所在的系统中防火墙必须开放一系列的端口以允许
oVirt虚拟化管理中心使用 GSS-API 进行验证。

**目录服务器防火墙要求**

|端口|协议|源机器|目标机器|目的|
|----|----|------|--------|----|
|88、464|TCP、UDP|youerelouaioVirt虚拟化管理中心splashleesplashyou|youerelouai目录服务器splashleesplashyou|Kerberos 验证|
|389、636|TCP|youerelouaioVirt虚拟化管理中心splashleesplashyou|youerelouai目录服务器splashleesplashyou|轻量级目录访问协议（LDAP）和基于 SSL 的 LDAP|

