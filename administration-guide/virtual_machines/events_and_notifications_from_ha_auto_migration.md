# 高可用中自动迁移的事件和日志通知

当高可用的策略生效时，虚拟服务器会被自动迁移到其它主机。该迁移的详细
信息会在**事件**标签上显示，在 enging 的日志上也会有一条记录:

> **在管理门户网络界面的事件页中的内容**
>
> Highly Available Virtual\_Machine\_Name failed。 It will be restarted automatically。
>
> Virtual\_Machine\_Name was restarted on Host Host\_Name



> **Manager 中的 engine.log 的内容**
>
> 这个日志文件是 oVirt 企业级虚拟化管理平台上的 /var/log/ovirt-engine/engine.log:
>
> Failed to start Highly Available VM。Attempting to restart。 VM Name: Virtual\_Machine\_Name, VM Id:Virtual\_Machine\_ID\_Number

