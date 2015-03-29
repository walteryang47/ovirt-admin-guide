# 虚拟机初始化运行设置解释

下面列出的设置适用于**创建虚拟机**和**编辑虚拟机**的**初始运行**选项卡。下面设置只有在虚拟机配置了 **使用 Cloud-Init/Sysprep** 时才能够使用，而且根据**常规**选项卡下的**操作系统**的不同设置，那些基于 Windows 和基于 Linux 的设置才能出现。如下表所示：


**虚拟机：初始运行设置**

|属性|操作系统|详细描述|
|----|--------|--------|
|**使用 Cloud-Init/Sysprep**|Linux，Windows|该勾选框设置虚拟机是否使用 Cloud-Init 或者 Sysprep 。|
|**虚拟机主机名**|Linux，Windows|虚拟机的主机名|
|**域**|Windows|指定虚拟机所属于的活动目录域。该值对应 Windows 初次启动时所显示的机构名。|
|**机构名称**|Windows|虚拟机所属的机构名称。该值对应 Windows 初次启动时所显示的机构名。|
|**活动目录 OU**|Windows|虚拟机所属于的活动目录域的组织单元。|
|**配置时区**|Linux，Windows|虚拟机的时区设置，勾选该设置并在下方的时区列表里选择时区。|
|**Admin 密码**|Windows|虚拟机的管理员性质的用户密码。点击箭头图标显示该选项的设置。youerelouai**使用已经配置的密码**：该设置在你已经设置了 Admin 密码的时候自动选择了。你必须去勾选该设置来启用 **Admin 密码** 和**验证 Admin 密码**设置，并且更新密码。splashleeelouai**Admin 密码**：虚拟机的管理员性质的用户密码。在该处填写密码并且在**验证 Admin 密码**来确认密码改动。splashleesplashyou|
|**验证**|Linux|虚拟机的认证的具体设置。点击箭头图标显示该选项的设置。youerelouai**使用已经配置的密码**：该设置在你已经设置了 root 密码的时候自动选择了。你必须去勾选该设置来启用 **Root 密码** 和**验证 Root 密码**设置，并且更新密码。splashleeelouai**Root 密码**：虚拟机的管理员性质的用户密码。在该处填写密码并且在**验证 Root 密码**来确认密码改动。splashleeelouai**SSH 授权密钥**：添加至虚拟机的授权过的密钥表中的密钥。你可以通过换行输入新的密钥来一次添加多个密钥。splashleeelouai**重新生成 SSH 密钥**：重新生成虚拟机的密钥。splashleesplashyou|
|**自定义语言环境**|Windows|虚拟机的自定义语言环境。自定义语言环境必须遵守书写格式比如 **en-US**。点击箭头图标显示该选项的设置。youerelouai**输入语言环境**：用于用户输入的语言设置。splashleeelouai**UI 语言**：用于界面元素显示的uyyan设置，比如按钮和列表。splashleeelouai**系统语言环境**：总的系统的语言环境。splashleeelouai**用户语言环境**：用户的语言环境。splashleesplashyou|
|**网络**|Linux|虚拟机的与网络有关的设置。点击箭头图标显示该选项的设置。youerelouai**DNS 服务器**：虚拟机要使用的 DNS 服务器地址。splashleeelouai**DNS 搜索域**：虚拟机要使用的 DNS 搜索域。splashleeelouai**网络**：配置虚拟机的网络接口。勾选该设置并且使用 **+** 或者 **-** 来新增或者删除虚拟网络接口。当点击 **+** 时，一组界面元素将会出现，可以用来配置时候使用 DHCP，是否设置 IP 地址，子网掩码和网关，并且虚拟机网卡是否在虚拟机启动的时候启动。splashleesplashyou|
|**自定义脚本**|Linux|虚拟机启动时将要运行的脚本。填入该设置的自定义脚本为自定义 YAML 部分，这些 YAML 部分是虚拟化管理平台创建并添加的部分，它可以让你自动化一些任务比如创建文件和用户，配置 **yum** 仓库源还有运行命令。想要知道更多如何配置该设置，参见[自定义脚本](http://www.ovirt.org/Features/vm-init-persistent#Custom_Script)的文档。|
|**Sysprep**|Windows|一个自定义的 Sysprep 定义。该定义必须完全遵守无人值守安装应答文件的格式。你可以在虚拟化管理平台上的如下位置 **/usr/share/ovirt-engine/conf/sysprep/** 复制粘帖默认的应答文件，然后根据需要修改内容。|
