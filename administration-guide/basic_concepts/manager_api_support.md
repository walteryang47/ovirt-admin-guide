# oVirt API 声明

oVirt 企业级虚拟化系统为和虚拟化环境中的组件进行交互，抛出了许多接口。这当然包括由 oVirt 企业级虚拟化管理中心的管理门户，用户门户和报表门户所提供的用户接口。其中一些接口是被 oVirt 完全支持的。但还有一些接口只支持只读访问或者只有在 oVirt 技术支持的特定要求下才会被支持。

## 读写访问都被支持的接口

对这些接口进行读写访问是完全被支持的。

- **Representational State Transfer(REST) API**

  oVirt 企业级虚拟化管理中心抛出的 REST API 在与 oVirt 企业级虚拟化管理中心进行交互时是完全被支持的。

- **Software Development Kit(SDK)**

  由 ovirt-engine-sdk-jave 和 ovirt-engine-sdk-python 软件包提供的 SDK 在与 oVirt 企业级虚拟化管理中心进行交互时也是被完全支持的。

- **Command Line Shell**

  由 vdsm-cli（对 node 进行操作） 和 ovirt-engine-cli（对 engine 进行操作） 软件包提供的命令行 shell 在与 oVirt 企业级虚拟化管理中心进行交互时是完全被支持的。

- **VDSM Hooks**

  oVirt 企业级虚拟化主机支持用于触发基于管理员门户中特别指定的自定义属性的虚拟机配置的变更的 VDSM hooks。运行 oVirt 虚拟化宿主机的虚拟主机上的 VDSM hooks 的使用现在还不被支持。

## 被支持的读访问接口

与这些接口的直接交互只局限于读访问。除非 oVirt 的技术支持有特别的要求，否则这些接口是不具备写访问权限的。

- **oVirt 企业级虚拟化管理中心的历史数据库**

  目前仅仅支持 oVirt Manager History Database 的读权限，写权限是不允许的。使用了管理指南中指定的数据库视图的 oVirt 企业级虚拟化管理中心中的历史数据库只支持读访问。不支持写访问。

- **虚拟主机上的 Libvirt**

  使用 **virsh -r** 命令对 **libvirt** 进行只读访问是一种被支持的和主机进行交互的方法。但不支持写访问。

## 不支持的接口

与以下接口进行直接交互是不被支持的，除非 oVirt 的技术支持对它有特殊的要求。不支持直接交互的接口有：

- **vdsClient 命令**

  除非 oVirt 的技术支持有特定要求，否则不支持使用 **vdsClient** 命令和虚拟主机进行交互。

- **oVirt 企业级虚拟化宿主机控制台**

  除了 oVirt 提供的一个基于文本的用户配置接口，其它的例如用控制台访问 oVirt 企业级虚拟化宿主机都是不允许的，除非有 oVirt 的技术支持的特殊要求。

- **oVirt 企业级虚拟化管理中心数据库**

  除非 oVirt 的技术支持要求，否则对 oVirt 企业级虚拟化管理中心数据库的直接访问与操作都是不被支持的。
