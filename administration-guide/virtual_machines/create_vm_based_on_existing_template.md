# 基于现成的模板创建虚拟机

**概述**

你可以基于模板创建虚拟机。这样允许你创建出来的虚拟机可以已经预包含虚拟机，虚拟网络接口，应用程序和其它的资源。


> **注意**
>
> 从模板创建出来的虚拟机取决于模板的配置。如果在系统中仍然有基于某个
> 模板创建的虚拟机，那么该模板是不能被删除的。因为这些虚拟机和模板
> 有关联关系。但是如果选择从模板克隆虚拟机，那么虚拟机和模板之间
> 就没有这些关联关系。


**基于模板创建虚拟机**

1. 点击**虚拟机**标签列出系统中的所有虚拟机。

2. 点击**新建虚拟机**按钮，打开**新建虚拟机**窗口。

3. 选择虚拟机需要运行在的**集群**。

4. 在**基于模板**下拉菜单中选择需要的模板。

5. 在**基于模板子版本**下拉菜单中选择需要的模板子版本。

6. 输入**名称**，**描述**，和**注释**。 其它保留默认(或者根据需要可以修改)。

7. 选择 **资源分配** 选项卡。

8. 在 **存储分配** 区域中选择 **Thin**。

9. 点击 **OK** 按钮。


**结果**

虚拟机已经创建好了，在虚拟机列表下会显示出来，用户可以开始使用这个虚拟机了。
