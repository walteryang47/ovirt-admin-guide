# 在新建集群策略和编辑集群策略中设置的解释

下表表示了在**新建集群策略**和**编辑集群策略**窗口中的详细配置项。

**新建集群策略和编辑集群策略的设置**

|属性名称|详细描述|
|--------|--------|
|**名称**|集群策略的名称。用于 oVirt 虚拟化管理中心索引集群策略。|
|**描述**|集群策略的描述。该属性建议填写但不要求填写。|
|**过滤器模块**|一个过滤器的集合，用来控制集群中的虚拟机能够运行在集群中的哪些主机上。启用一个过滤器将导致选择虚拟机运行的候选主机中去除掉不符合该过滤器的主机。如下详述：youerelouai**PinToHost**：虚拟机没有专门运行在的主机。splashleeelouai**CPU-Level**：不符合虚拟机的 CPU 拓扑的主机。splashleeelouai**CPU**：没有虚拟机所要求的 CPU 数量的主机。splashleeelouai**Memory**：没有足够内存资源运行虚拟机的主机。splashleeelouai**VmAffinityGroups**：没有符合虚拟机所在的 Affinity 组的主机。例如，Affinity 组里的虚拟机必须要运行在不同的集群中。splashleeelouai**HA**：强制 hosted engine 虚拟机运行在 Hosted Engine HA 的值为正的主机上splashleeelouai**Network**：没有完全包含虚拟机的网卡所需要的逻辑网络的主机，或者集群的显示网络没有安装的主机。splashleesplashyou|
|**Weights 模块**|一个权重模块的集合，控制决定虚拟机运行在的主机的相对优先级队列。youerelouai**OptimalForHaReservation**：根据主机的高可用分数来设置权重值。splashleeelouai**None**：依照负载均衡模块决定权值。splashleeelouai**OptimalForEvenGuestDistribution**：依照主机运行的虚拟机数量决定权值。splashleeelouai**VmAffinityGroups**：根据虚拟机的 Affinity 组来决定权值。该权重模块决定了虚拟机根据 Affinity 组运行在同一台主机还是不同主机的趋势度，趋势度可以由调节该模块的参数来控制。splashleeelouai**OptimalForPowerSaving**：依照主机 CPU 使用率决定权值。主机 CPU 使用率高的有更高的权限。splashleeelouai**OptimalForEvenDistribution**：依照主机 CPU 使用率决定权值。主机 CPU 使用率低的有更高的权限。splashleeelouai**HA**：依照主机的高可用分数决定权值。splashleesplashyou|
|**负载平衡器**|该下拉列表框允许你选择一个负载平衡器来应用。负载平衡器模块决定了从使用率高的主机迁移虚拟机到使用率低的主机所使用的逻辑。|
|**属性**|该下拉列表框允许你给负载平衡器添加或者移除属性。默认没有属性设置，可以设置的属性与具体的负载平衡器有关，使用 **+** 或者 **-** 按钮来给一个负载平衡器增加或者移除属性。|
