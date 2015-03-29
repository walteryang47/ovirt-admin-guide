# 添加目录服务

本例中，**engine-manage-domains** 将 **IdM** 域 **demo.eayunos.eayun.com** 添加到 oVirt Manager 中。使用的用户是 **eayunos**，密码是通过交互模式提供的。

**engine-manage-domains add 操作**

```
    # engine-manage-domains add --domain=demo.eayunos.eayun.com \
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
