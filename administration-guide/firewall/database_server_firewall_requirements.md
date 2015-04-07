# 数据库服务器防火墙要求

oVirt虚拟化管理中心支持使用远程的数据库服务器。如果您在 oVirt
中使用远程的数据库，则必须确保远程的数据库服务器允许来自
oVirt虚拟化管理中心的连接。

**数据库服务器防火墙要求**

|端口|协议|源机器|目标机器|目的|
|----|----|------|--------|----|
|5432|TCP、UDP|youerelouaioVirt虚拟化管理中心splashleesplashyou|youerelouaiPostgreSQL 数据库服务器splashleesplashyou|PostgreSQL 数据库的默认连接端口|

如果您准备把数据库安装在 oVirt 企业级虚拟化管理中心 本身所在的系统上时(这是安装时的默认选项),就不需要配置额外的防火墙规则。
