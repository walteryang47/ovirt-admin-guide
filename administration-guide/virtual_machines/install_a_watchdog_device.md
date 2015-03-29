# 安装一个看门狗设备

**概述**

要激活附加到虚拟机上的看门狗设备，你必须在虚拟机上安装看门狗的软件包并且启动 **watchdog** 服务。


**安装一个看门狗设备**

1. 登录到附加了看门狗设备的虚拟机上。

2. 运行如下的命令来安装看门狗软件包及其依赖：

   ```# yum install watchdog```

3. 编辑 **/etc/watchdog.conf** 文件并且取消如下行的注释：

   ```watchdog-device = /dev/watchdog```

4. 保存更改。

5. 运行如下命令来启动 **watchdog** 服务，并且保证服务随着开机启动：

   ```
   # service watchdog start
   # chkconfig watchdog on
   ```

**结果**

你成功地在虚拟机上安装并启动了看门狗。
