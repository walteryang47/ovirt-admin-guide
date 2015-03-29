# 虚拟机资源分配设置解释

下面列出的设置适用于**创建虚拟机**和**编辑虚拟机**的**资源分配**选项卡。


**虚拟机：资源分配设置**

|参数|子元素|描述|
|----|------|----|
|**CPU 分配**|**CPU 共享**|允许用户设置相当于其他虚拟机，这台虚拟机能使用的 CPU 资源。youerelouai**低** - 512splashleeelouai**中** - 1024splashleeelouai**高** - 2048splashleeelouai**自定义** - 由用户定义具体的数值。splashleesplashyou|
||**CPU pinning 拓扑结构**|该选项能使得虚拟机的虚拟 CPU（vCPU）运行在物理主机的物理 CPU（pCPU） 上。CPU pinning 的语法为 **v#p[_v#p]**，使用方法为：youerelouai**0#0** - 绑定 vCPU 0 和 pCPU 0。splashleeelouai**0#0_1#3** - 绑定 vCPU 0 和 pCPU 0, 同时绑定 vCPU 0 和 pCPU 3。splashleeelouai**1#1-4,^2** - 绑定 vCPU 0 和 pCPU 1-4中的一个，除了物理 CPU 2。splashleesplashyou为了能绑定 vCPU 和 pCPU，**迁移设置**必须选择**不允许迁移**，并且勾选**使用主机 CPU** 勾选框。|
|**内存分配**||保证分给虚拟机的物理内存数量。|
|**存储分配**||只有从模板创建的虚拟机才能使用模板 Provision 选项。|
||**Thin**|该类型只有需要时候才会发生存储的分配，这种类型的分配是对空间的优化，比 clone 的性能要差一点。|
||**Clone**|在创建磁盘初始，就完成了所有磁盘的分配，比 Thin 的读写速度要高, 不过空间占用比 Thin 的多。|
||**启用 VirtIO-SCSI**|是否启用 VirtIO-SCSI 的控制器。|
