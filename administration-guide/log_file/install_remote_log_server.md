# 安装远程日志服务器

**概要**

将 oVirt 企业级虚拟化环境中的日志保存在统一的日志服务器更有利于调试以及故障排除。

在日志服务器上按照下面的步骤进行操作，可以单独安装一台日志服务器或者直接在 oVirt Manager 上进行配置。

**安装虚拟化主机日志服务器**

1. 配置 SELinux，允许 rsyslogd 进行网络传输

```
    # semanage port -a -t syslogd_port_t -p udp 514
```

1. 编辑 **/etc/rsyslog.conf**，增加以下配置：

```
    $template TmplAuth, "/var/log/%fromhost%/secure"
    $template TmplMsg, "/var/log/%fromhost%/messages"
    $RuleSet remote
    authpriv.*
    ?TmplAuth
    *.info,mail.none;authpriv.none,cron.none
    $RuleSet RSYSLOG_DefaultRuleset
    $InputUDPServerBindRuleset remote
```

  取消下面2行的注释：

```
    #$ModLoad imudp
    #$UDPServerRun 514
```

1. 重启 rsyslog 服务：

```
    # service rsyslog restart
```

**结果**

日志服务器可以接受 oVirt Node 服务器的日志（**messages** 和 **secure** 这2个日志文件中的日志类型）。
