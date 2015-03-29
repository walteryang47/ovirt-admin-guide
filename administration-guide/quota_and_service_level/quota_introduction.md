# 配额简介

配额是 oVirt 企业级虚拟化管理中心中提供的一个对资源的使用进行限制的工具。配额可以被认为是基于用户权限限制层之上对资源进行的进一步的限制。

配额是一个数据中心的对象。

oVirt 环境的管理员可以通过配额来限制用户对内存、CPU 和存储的访问。配额定义了管理员可以分配给用户的内存资源和存储资源的限制，而用户只能使用限额内的资源。当配额内的资源被用完后，oVirt 虚拟化管理中心将不再允许用户进行操作。

配额分为以下两种类型：

**两个不同类型的配额**

|配额类型|定义|
|--------|----|
|**运行时配额（Run-time Quota）**|限制对运行时资源（例如 CPU 和内存）使用的配额。|
|**存储配额**|这种类型的配额限制可用的存储空间。|

配额与 SELinux 类似，有三种模式：

**配额的三种模式**

|配额模式|功能|
|--------|----|
|**强制的（Enforced）**|此模式具体实施您在审计模式设置的配额，限制受配额影响的用户或者用户组所使用的资源。|
|**审计（Audit）**|此模式允许您更改配额设置。选择此模式来增加或者减少受配额影响的用户可用的运行时配额和存储配额的大小。|
|**禁用的（Disabled）**|此模式取消配额定义的运行时和存储资源限制。|

当用户尝试运行虚拟机时，该虚拟机的硬件规格将会与所应用的配额中的存储和运行时资源限额进行比较。

如果启动虚拟机将会使得受一个配额限制的所有运行中虚拟机所用资源的总量超过配额中所定义的限额，oVirt 虚拟化管理中心将拒绝运行该虚拟机。

当用户创建一个新磁盘时，请求的磁盘大小将会加入到其它受同样一个配额限制的磁盘的使用总量中。如果该新建的磁盘使得磁盘使用的总量超过配额中允许的限额，磁盘的创建将会失败。

配额为同一硬件上的资源共享提供了可能。配额同时支持硬阈值（hard threshold）和软阈值（hard threshold）。管理员能够使用配额来为资源设置阈值。这些阈值在用户看起来是全部的可用资源。为了避免用户意外超过阈值时的操作失败，oVirt
还允许使用超过阈值一定的“额外（grace）”大小。当用户使用的资源超过阈值时，系统会给用户发送一条警告信息。

> **重要**
>
> 配额强制限制运行中的虚拟机所使用的资源。忽略这些限制将有可能导致出现您使用不了虚拟机或者虚拟磁盘的情况。
>
> 当配额运行在强制（enforced）模式下时，未被分配配额的虚拟机和虚拟磁盘将不能够被使用。
>
> 必须为虚拟机分配一个限额才能够启动该虚拟机。
>
> 必须为虚拟机拥有的磁盘分配限额，才能为虚拟机创建快照。
>
> 当从虚拟机创建模板时，您将会被提示选择该模板使用哪个配额。这将允许您设置该模板（以及之后基于该模板创建的虚拟机）与用以生成模板的虚拟机及磁盘使用不同的配额。
