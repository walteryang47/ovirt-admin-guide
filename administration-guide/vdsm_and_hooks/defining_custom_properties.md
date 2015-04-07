# 定义自定义属性

oVirt 企业级虚拟化管理中心接受并将其传至自定义 Hook 脚本的自定义属性，是通过
`engine-config` 命令进行定义的。在安装了 oVirt 企业级虚拟化管理中心的主机上使用
**root** 用户运行此命令。

**UserDefinedVMProperties** 和 **CustomDeviceProperties**
配置键用以存放支持的自定义属性名称。定义了每个自定义属性的合法输入值的正则表达式也存放在这些配置键中。

多个自定义属性之间使用分号分隔。请注意当设置配置键时，其包含的已存在的值将会被覆盖。当需要将新的自定义属性添加到原有的自定义属性列表之中时，命令中必须包含所有用以设置配置键的值的自定义属性。

一旦配置键的值被更新，**ovirt-engine**
服务必须重启以使得新的自定义属性生效。

## 示例：虚拟机属性 - 定义 smartcard 自定义属性

1.  使用以下命令检查已存在的使用 **UserDefinedVMProperties**
    配置键定义的自定义属性：

        # engine-config -g UserDefinedVMProperties

    如下面的输出所示，自定义属性 **memory** 已经被定义了。正则表达式
    **\^[0-9]+\$** 确保了该自定义属性的值只能够包含数字。

        # engine-config -g UserDefinedVMProperties
        UserDefinedVMProperties: version: 3.0
        UserDefinedVMProperties: version: 3.1
        UserDefinedVMProperties: version: 3.2
        UserDefinedVMProperties: version: 3.3
        UserDefinedVMProperties : memory=^[0-9]+$ version: 3.2

2.  由于 **memory** 自定义属性已经在 **UserDefinedVMProperties**
    配置键中定义，新的自定义属性必须被添加到其之后。新增的自定义属性
    **smartcard** 将被添加到配置键的值中。该自定义属性将接受值为 **true**
    或者 **false** 的输入。

        # engine-config -s UserDefinedVMProperties='memory=^[0-9]+$;smartcard=^(true|false)$' --cver=3.2

3.  验证使用 **UserDefinedVMProperties**
    配置键定义的自定义属性被正确地更新了。

        # engine-config -g UserDefinedVMProperties
        UserDefinedVMProperties: version: 3.0
        UserDefinedVMProperties: version: 3.1
        UserDefinedVMProperties: version: 3.2
        UserDefinedVMProperties: version: 3.3
        UserDefinedVMProperties : memory=^[0-9]+$;smartcard=^(true|false)$ version: 3.2

4.  最后，**ovirt-engine** 服务必须重启以使得配置的改动生效。

        # service ovirt-engine restart

## 示例：设备属性 - 定义 interface 自定义属性

1.  使用以下命令检查已存在的使用 **CustomDeviceProperties**
    配置键定义的自定义属性：

        # engine-config -g CustomDeviceProperties

    如下面的输出所示，没有已被定义的自定义属性。

        # engine-config -g CustomDeviceProperties
        CustomDeviceProperties: version: 3.0
        CustomDeviceProperties: version: 3.1
        CustomDeviceProperties: version: 3.2
        CustomDeviceProperties: version: 3.3

2.  **interface**
    自定义属性并不存在，所以可以直接被添加。在这个例子中，子属性**speed**
    的有效值被设置为由一到五位数的一个范围，而子属性 **duplex**
    的有效值被设置为 **full** 或者 **half**。

        # engine-config -s CustomDeviceProperties="{type=interface;prop={speed=^([0-9]{1,5})$;duplex=^(full|half)$}}" --cver=3.3

3.  验证使用 **CustomDeviceProperties**
    配置键定义的自定义属性被正确地更新了。

        # engine-config -g CustomDeviceProperties
        UserDefinedVMProperties: version: 3.0
        UserDefinedVMProperties: version: 3.1
        UserDefinedVMProperties: version: 3.2
        UserDefinedVMProperties : {type=interface;prop={speed=^([0-9]{1,5})$;duplex=^(full|half)$}} version: 3.3

4.  最后，**ovirt-engine** 服务必须重启以使得配置的改动生效。

        # service ovirt-engine restart


