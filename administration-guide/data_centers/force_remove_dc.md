# 强制删除数据中心

**概述**

当主机变为 **NonResponsive** ，或者附加在该数据中心上的存储发生错误的时候，数据中心的状态会变为 **NonResponsive** 。此时是无法按照正常的删除数据中心的流程来删除数据中心的。

**强制删除**不需要数据中心有活动的主机。用该种方式删除存储后，相关联的存储也会被永久删除。

在强制删除数据中心之前可能需要把出错的存储先**销毁**。

**强制删除数据中心**

1. 点击**数据中心**标签，选择需要删除的数据中心。

2. 点击**强制删除**打开**强制删除数据中心**窗口。

3. 勾选**批准操作**。

4. 点击**确定**强制删除数据中心。

**结果**

数据中心和相关联的存储域将会从 oVirt 环境中被永久删除。
