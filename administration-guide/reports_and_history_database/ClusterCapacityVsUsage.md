# 执行报表：ClusterCapacityVsUsage

**Cluster Capacity Vs Usage** 报表显示了在给定时间中的系统容量和使用（工作量）。容量表现在了 CPU 内核和物理内存上，然而使用则表现在了虚拟内核和虚拟 CPU 上。运行这个报表需要用到以下参数：

**Cluster Capacity Vs Usage Parameters**

| 参数 | 描述 |
| ---- | ---- |
| **显示已删除的实体** | 报表包含了已删除的对象，例如已从环境中移除的数据中心，集群和主机。 |
| **日期范围** | 为报表选择日期范围。按日报表包含了一整天的报表数据。按月报表包含了一个月的报表数据。按季度报表包含了三个月的报表数据，并且起始月份可以在**日期**参数中指定。按年报表包含了一年的报表数据，起始月份也在**日期**参数中进行定义。 |
| **日期** | 报表累积了日期范围内的所有数据，并且是从当前日期开始。按日日其范围的增量是一天。按月日期范围使用的是所选月份。季度日期范围是由所选择的起始月份决定的。按年日期范围是由选选择的起始月份开始的。 |
| **数据中心** | 报表只包含了选定数据中心中的虚拟机。选项列表只显示有虚拟机的数据中心。 |
| **集群** | 报表只包含被选中的集群。选项列表只会显示选定数据中心下的集群。如果选择了**所有**，那么报表会包含选定数据中心下的所有集群。 |