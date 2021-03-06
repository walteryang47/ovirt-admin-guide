#oVirt 存储域

oVirt使用集中化的存储系统来存储虚拟机镜像、ISO
文件和虚拟机快照等。存储域是通过以下技术来实现的：

-   NFS

-   GlusterFS

-   其它兼容 POSIX 的文件系统

-   iSCSI

-   本地文件夹

-   FCP

-   pNFS

存储域是建立数据中心的一个先决条件，只有在存储域添加并激活之后，数据中心才能被初始化。

oVirt
平台让用户能够通过管理员门户的**存储**标签对存储进行分配及管理。**存储**标签下将列出所有的存储域，详情面板中将列出存储域的具体信息。

目前，oVirt 有三种类型的存储域：

-   **数据存储域**：数据存储域用以存放数据中心中的虚拟机和模板的虚拟磁盘镜像及
    OVF 文件，同时还用以存储虚拟机的快照。

    数据存储域不能在不同的数据中心中共享。并且数据存储域的类型要和数据中心的类型一致，只有在数据存储域被添加到了数据中心之后，其它类型的存储域才能被添加。

-   **ISO 存储域**：存放 ISO 镜像文件，可以在不同的数据中心中共享。ISO
    存储域使得数据中心不需要使用物理的光盘等设备。

-   **导出域**：是一个临时的存储域，主要用来在不同的数据中心和 oVirt
    虚拟化管理平台之间复制和移动镜像文件。导出域可以用来备份虚拟机，虽然导出域可以在不同的数据中心间移动，但是同一时间只能在一个数据中心中被激活。

> **重要**
>
> 现在，我们不再支持使用非 NFS 作为后台存储的导出域。那些从 oVirt 企业级虚拟化环境导入的，已经存在的输出存储域仍然被支持，但新的导出存储域必须是 NFS 存储。

在开始为您的数据中心配置和附加存储前，您需要先决定数据中心所需要的存储类型。


> **重要**
>
> 要添加存储域，用户必须通过管理员门户登录，并且数据中心中必须有至少有一台主机处于
> *Up* 状态。


