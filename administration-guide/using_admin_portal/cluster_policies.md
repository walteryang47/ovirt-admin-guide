# 集群策略

集群策略就是一组规则，它定义了虚拟机在应用这个策略的集群中的主机间的分配逻辑。集群策略通过使用过滤器（filter）、权重（weighting）和负载均衡（load balancing）策略来定义这个分配逻辑。Red Hat Enterprise Virtualization Manager 提供了 4 个默认的集群策略 - **Evenly_Distributed**、**None**、**Power_Saving** 和 **VM_Evenly_Distributed**。您也可以通过定义新的集群策略来实现对虚拟机分配逻辑的细化。
