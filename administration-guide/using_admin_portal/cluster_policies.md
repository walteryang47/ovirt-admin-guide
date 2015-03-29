# 集群策略

集群策略是一组规则的集合，它定义了集群中主机上分布的虚拟机使用资源的逻辑。该逻辑通过组合过滤器，weightings  以及负载均衡策略来实现。  oVirt  虚拟化管理中心提供了4个默认的集群策略：**evenly_distributed**、**none**、**power_saving**和**vm_evenly_distributed**。也可以自定义新的集群策略来为分布的虚拟机提供更精细的控制。

