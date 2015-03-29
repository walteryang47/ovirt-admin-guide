# 共享磁盘

有些应用程序要求在服务器之间共享存储资源。oVirt
管理中心统有一个选项可以把虚拟机磁盘标记为
**可共享的**。这样，一个虚拟磁盘就可以同时被多个虚拟机访问和共享了。

共享磁盘并不能在所有情况都使用。对于集群化的数据库或者其他高可用业务，使用共享磁盘是合适的。而对于非集群话的多台虚拟机来说，由于它们的读写没有进行相互的协调，将可能造成数据不一致。

另外，用户不能对共享磁盘做快照。做了快照的虚拟磁盘也不能标记为可共享的。

您可以在创建磁盘或者编辑磁盘时将一个磁盘标记为可共享的。
