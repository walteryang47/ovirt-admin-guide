# 日志收集工具的使用示例

当执行 **engine-log-collector** 命令而不添加任何参数时，默认会收集 oVirt Manager 和附加在其上的主机的所有日志。这个命令也会收集数据库日志，除非使用了 ***-no-postgresql*** 参数。下面使用日志收集工具的示例：

> **日志收集工具的使用**
>
```
    # engine-log-collector
    INFO: Gathering oVirt Engine information...
    INFO: Gathering PostgreSQL the oVirt Engine database and log files from
    localhost...
    Please provide REST API password for the admin@internal oVirt Engine user
    (CTRL+D to abort):
    About to collect information from 3 hypervisors. Continue? (Y/n):
    INFO: Gathering information from selected hypervisors...
    INFO: collecting information from 192.168.122.250
    INFO: collecting information from 192.168.122.251
    INFO: collecting information from 192.168.122.252
    INFO: finished collecting information from 192.168.122.250
    INFO: finished collecting information from 192.168.122.251
    INFO: finished collecting information from 192.168.122.252
    Creating compressed archive...
    INFO Log files have been collected and placed in /tmp/sosreport-LogCollector-20140428171306.tar.xz.
    The MD5 for this file is be89822f20719d1094a39bc9ced3df49 and its size is 38.2M
```
