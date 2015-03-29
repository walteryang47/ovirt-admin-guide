# 验证目录服务

本例中，**engine-manage-domains** 对 oVirt Manager 中的目录服务进行验证。验证方法是根据配置文件中每一个目录服务的验证信息进行登录尝试，如果成功登录则说明目录服务可用。

**engine-manage-domains validate 操作**

```
    # engine-manage-domains validate
    Domain ovirt.test.com is valid.
    The configured user for domain ovirt.test.com is ovirt@OVIRT.TEST.COM
    Manage Domains completed successfully
```
