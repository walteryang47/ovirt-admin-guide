# 导入虚拟机磁盘

**概述**

虚拟磁盘镜像是被OpenStack镜像服务管理的，如果OpenStack镜像服务作为外部供应商被添加到了oVirt虚拟化管理端，则可以导入虚拟磁盘。

1. 点击**存储**资源标签，在显示的结果列表中选择OpenStack镜像服务域。

2. 点击详细面板中的**映像**标签，在镜像列表中选择要导入的镜像。

3. 点击**导入**，并打开**导入镜像**窗口。

4. 在下拉菜单中选择虚拟磁盘镜像要导入的数据中心。

5. 在下拉菜单中选择虚拟磁盘镜像所在的存储域。

6. 另外还可以在配额下拉菜单中选择一个为该磁盘镜像申请的配额。

7. 点击**确定**导入镜像。

**结果**

该镜像作为一个浮动磁盘被导入，并且显示在磁盘列表中，现在可以将它附加到一个虚拟机上了。

