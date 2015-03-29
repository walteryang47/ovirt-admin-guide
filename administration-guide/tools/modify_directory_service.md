# 修改目录服务

本例中，**engine-manage-domains** 对 **IdM** 域 **demo.eayunos.eayun.com** 的配置进行了更改。更改完成之后，oVirt Manager 查询目录服务时使用新的用户 **eayunos**。命令执行时密码通过交互模式提供。

**engine-manage-domain edit 操作**

```
    # engine-manage-domains edit --domain=demo.eayunos.eayun.com \
    --provider=IPA --user=eayunos --interactive
    loaded template kr5.conf file
    setting default_tkt_enctypes
    setting realms
    setting domain realm
    success
    User guid is: 6d580ef5-130a-4931-bcd0-23bd23028ece
    Successfully added domain demo.eayunos.eayun.com. oVirt Engine restart is
    required in order for the changes to take place (service ovirt-engine restart).
```
