# 网络标签

网络标签极大的简化了许多管理任务，这些任务大多和创建管理逻辑网络相关，还和那些逻辑网络是如何与物理主机网卡和网络高可用联系相关。

每个网络标签都是一个纯文本，人类可读标签可以被附加到一个逻辑网络或者一个物理主机网卡上。标签的长度没有严格的限制，但是您所输入的必须是大小写字母，下划线和连字符相结合的字符串；不允许使用空格或特殊字符。

将一个标签附加到一个逻辑网络或物理主机网卡上时会创建一个与其它标记了相同网络标签的逻辑网络或物理主机网卡的联系，例如：

**网络标签关联规则**

* 如果您将一个标签附加到一个逻辑网络上，凡是带有相同网络标签的物理主机网卡都会和该逻辑网络联系起来。

* 如果您将一个标签附加到一块物理主机网卡上，凡是带有相同网络标签的逻辑网络都会自动和该物理主机网卡联系起来。

* 改变一个已经附载到一个逻辑网络或物理主机网卡上的网络标签的行为和删除一个网络标签与添加一个新的网络标签是相同的。相关逻辑网络或物理主机网卡之间的关系也会随之改变。


**网络标签和集群**

* 如果一个已经标记了的逻辑网络添加到了一个集群中，并且在该集群中有一块带有相同网络标签的物理主机网卡的话，该逻辑网络会被自动添加到那块物理主机网卡上。

* 如果一个已经标记了的逻辑网络从一个集群中分离出去，并且在该集群中有一块带有相同网络标签的物理主机网卡的话，该逻辑网络会被自动从那块物理主机网卡上分离出去。


**网络标签和拥有角色的逻辑网络**

* 如果一个已经标记了的逻辑网络被分配来扮演显示网络或迁移网络的角色，然后该逻辑网络会在使用了 DHCP 的物理主机网卡上进行配置，这样便可以为该逻辑网络分配一个 IP 地址。