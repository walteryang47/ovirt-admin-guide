# 类型

类型定义一个虚拟机的硬件配置，当创建或者编辑虚拟机时选择一个类型，虚拟机硬件配置的字段将会自动填写该类型定义的值。用户可以用它来创建多个硬件配置想同的虚拟机，而不需要手动填写每个字段。

默认情况下有一组预定义的类型可供选择，如下表所示：

**预定义类型**

|名称|内存|虚拟CPU总数|
|----|----|-----------|
|Large|8GB|2|
|Medium|4GB|2|
|Small|2GB|1|
|Tiny|512MB|1|
|XLarge|16GB|4|

管理员可以在**配置**窗口的**类型**标签下创建、编辑、删除类型。

![配置窗口](images/Instance-Types.png)

当新建或者编辑虚拟机时，如果窗口中的**类型**字段绑定一个特定类型，则一些属性字段左边会出现一个连接图标，如果有属性字段被更改，则左边的连接图标会显示成断开，该类型将自动与虚拟机分离。如果将更改的字段值再改回去，则恢复原先所选的**类型**连接。

