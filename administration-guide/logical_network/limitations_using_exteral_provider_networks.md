# 使用外部供应商网络的限制

使用 oVirt 虚拟化管理中心中从外部供应商导入的逻辑网络会有一下限制：

-   外部供应商提供的逻辑网络只能被用作虚拟机网络，不能用于显示网络。

-   同一逻辑网络能够被导入多次，但只能导入到不同的数据中心中。

-   您不能在 oVirt 虚拟化管理中心中编辑外部供应商提供的逻辑网络。为了编辑由外部供应商提供的一个逻辑网络的详细信息，您必须在提供了该逻辑网络的 OpenStack 网络服务上对其进行直接修改。

-   端口镜像不适用于连接到外部供应商提供的逻辑网络的虚拟网卡。和外部供应商所提供的逻辑网络相连的虚拟网卡不支持端口镜像(Port mirroring)功能。

-   如果有虚拟机使用着外部供应商所提供的逻辑网络，由于该逻辑网络正在被虚拟机使用，所以该供应商无法从 oVirt 虚拟化管理中心中删除。

-   外部供应商提供的网络不是“必需的”网络。正是因为这样，导入了这类逻辑网络的集群的调度工作在选择主机时将不会考虑这类网络的情况。另外，用户需要确保在导入了这类逻辑网络的集群中的主机上该逻辑网络的可用性。

> **重要**
>
> 由外部供应商导入的逻辑网络只和 oVirt 兼容，它并不能分配到运行在 oVirt 企业级虚拟化宿主机的虚拟机上。

