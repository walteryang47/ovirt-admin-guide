# 删除目录服务

本例中，**engine-manage-domains** 从 oVirt Manager 中删除 **IdM** 域 **demo.eayunos.eayun.com** 的配置。更改完成之后， oVirt Manager 中属于 **demo.eayunos.eayun.com** 的用户将无法登录，但是依然会保留在用户列表中，除非手动清理用户列表。

本例中要删除的目录服务是 oVirt Manager 中的最后一个，所以命令执行过程中会给出一个警告，提醒用户最后一个目录服务删除之后，只有 **admin@internal** 用户可以登录到 Manager，新的用户只能在添加新的目录服务之后手动添加。

**engine-manage-domains delete 操作**

```
    # engine-manage-domains delete --domain=demo.eayunos.eayun.com
    WARNING: Domain directory.demo.redhat.com is the last domain in the
    configuration. After deleting it you will have to either add another domain, or
    to use the internal admin user in order to login.
    Successfully deleted domain demo.eayunos.eayun.com. Please remove all users
    and groups of this domain using the Administration portal or the API.
```
