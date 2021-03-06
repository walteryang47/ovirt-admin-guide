# 给一个对象分配配额

**概述**

此过程展现如何将配额与虚拟机联系起来，即分配该配额至虚拟机对象。

**为一个虚拟机设置配额**

1. 在主面板中选择您计划分配配额到其之上的虚拟机。

1. 点击**编辑**打开**编辑虚拟机**窗口。

1. 使用**配额**下拉菜单选择您希望该虚拟机消耗的配额。

1. 点击**确定**。

**结果**

成功的将配额分配到您所选择的虚拟机上。

**概述**

此过程展现如何分配配额至虚拟机磁盘。

**为虚拟机磁盘设置配额**

1. 在主面板中选择您计划分配配额到其磁盘之上的虚拟机。

1. 在详情面板中选择您计划分配配额到其之上的磁盘。

1. 点击**编辑**打开**编辑虚拟磁盘**窗口。

1. 使用**配额**下拉菜单选择您希望该虚拟磁盘消耗的配额。

1. 点击**确定**。

**结果**

您成功的将配额分配到您所选择的虚拟磁盘上。

> **重要**
>
> 必须为一个虚拟机所联系的所有对象都选择配额，该虚拟机才能够工作。如果您为虚拟机所联系的一个对象选择配额失败，该虚拟机将不能够正常工作。这种情况下在 oVirt 企业级虚拟化管理中心抛出的错误将会是很一般的错误，造成很难知道该错误是由于您未为虚拟机所联系的所有对象都选择配额产生的。在虚拟机没有指定的配额时是无法对虚拟机进行快照的。同样的，在虚拟机的虚拟磁盘没有指定的配额时，是无法从该虚拟机创建模板的。

