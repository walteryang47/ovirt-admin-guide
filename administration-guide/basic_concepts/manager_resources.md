
# oVirt 资源

总的来讲，oVirt 企业级虚拟化环境的资源分为以下两类:物理资源和逻辑资源。顾名思义，物理资源指的是那些物理存在的资源，比如主机和存储服务器。相反的，逻辑资源是指非物理存在的资源，比如逻辑网络和虚拟机模板等。

-   **数据中心** - 数据中心是 oVirt 系统中最高级别的容器，它包含了所有物理资源和逻辑资源。它是集群，虚拟机，存储和网络的集合。

-   **集群** - 一个集群指的是多个物理主机的集合，它可以看作是一个为虚拟机提供资源的资源池。在同一个集群中的主机共享相同的网络架构和存储设备。它们组成了一个迁移域，虚拟机可以在这个迁移域中的主机之间进行迁移。

-   **逻辑网络** - 逻辑网络是物理网络在逻辑上的表示，它把 oVirt 虚拟化管理中心，主机，存储和虚拟机之间的网络流量和通信分成不同的组，从而更好的实现网络的管理和流量的分离。

-   **主机** - 主机就是一个物理服务器，其上可以运行一个或多个虚拟机，主机会被组成不同的集群。虚拟机可以在同一个集群的不同的主机之间进行迁移。

-   **存储池** - 存储池是一个逻辑上的概念，它包含了一个特定存储类型（如 iSCSI，Fibre Channel，NFS 或 POSIX）的一个单独的映像存储仓库。每个存储池都可以包含多个存储域，用来存储虚拟机磁盘镜像，ISO 镜像还可以用于导入/导出虚拟机磁盘镜像。

-   **虚拟机** - 虚拟机就是一个包括了操作系统和一组应用程序的虚拟桌面或虚拟服务器。一个**虚拟机池**中可以创建多个相同的虚拟机。一般用户只能访问虚拟机，只有拥有特性权限的用户才可以创建，管理或删除虚拟机。

-   **模板** - 模板就是一个包括了一些预定义设置的虚拟机模型。基于一个特定模板的虚拟机会继承模版中的设置。使用模板，是一个一步实现创建大量虚拟机的快捷方式。

-   **虚拟机池** - 虚拟机池是指一组相同的虚拟机的集合。虚拟机池可以用来满足不同成员的不同需求。虚拟机池可以基于不同目的而创建。比如为市场部门创建一个专用的虚拟机池，而为研发部门创建另一个虚拟机池，等等。

-   **快照** - 快照是指在某一个时间点虚拟机操作系统和其所有应用程序的一个记录。快照有很多用途，比如在系统升级或者安装新应用程序之前，可以创建快照来保存当前虚拟机的设置。一旦操作期间出现问题，可以利用快照将虚拟机恢复到原来的状态。

-   **用户类型** - oVirt 企业级虚拟化系统支持多级别的管理员和用户，不同级别的管理员和用户拥有不同级别的权限。系统管理员可以管理物理基础设施中的各个方面，比如数据中心，主机和存储。用户在获得了相应权限后，可以使用虚拟机池中的可用虚拟机或是一台单独的虚拟机。
 
-   **事件和监控** - 与事件相关的警告和其它提示可以帮助管理员监控所有资源的性能和状态。

-   **报表** - 报表可能是基于 JasperReports 的报表模块所产生的各种报表还有可能是从数据仓库中获得的报表。报表模块可以生成预定义或特设的报表。用户还可以在收集了主机，虚拟机和存储的监控数据的数据仓库中使用任何支持 SQL 语言的查询工具来生成报表。