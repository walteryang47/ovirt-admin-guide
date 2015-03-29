# 搜索语法和例子

oVirt 中对资源进行搜索的搜索查询条件的语法如下所示：

*搜索结果类型: {搜索规则} [sortby 排序方式]*

以下的例子展示了如何使用搜索查询条件并帮助您理解 oVirt
是如何帮助构造搜索查询条件的。

**语法示例**

|例子|结果|
|----|----|
|Hosts: Vms.status = up|显示所有运行着虚拟机的主机列表。|
|Vms: domain = dev.test.com|显示在某个特定的域中所有运行的虚拟机列表。|
|Vms: user.name = Dunrong|显示所有属于名为 Dunrong 的用户的虚拟机列表。|
|Events: severity \> normal sortby time|显示按时间排序的所有严重程度高于 normal 的事件列表。|
