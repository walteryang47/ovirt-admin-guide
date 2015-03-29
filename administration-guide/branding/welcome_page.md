# 欢迎页

欢迎页就是您访问 oVirt虚拟化管理中心 的主页时初始显示的页。您除了可以定制它的外观和风格,您还可以通过编辑一个模板文件来对它进行其它的一些修改,如在这个页中添加额外的链接。欢迎页的以下项可以被定制:

- 页的标题

- 页头(左、中和右)

- 错误信息

- 向前的链接以及与那个链接相关的文字信息

欢迎页的 class 位于 **welcome_style.css** 文件中。

**模板文件( Template File)**

欢迎页的模板文件是一个名为 **welcome_page.template** 的普通 HTML 文件,它不包括 **HTML**、**HEAD** 和**BODY** tag。这个文件会被直接插入到欢迎页中,作为要在欢迎页中显示的信息的容器。因此,您需要通过编辑这个文件来修改欢迎页中的信息或为它添加链接。另外,模板文件还提供了替代符(如**{user_portal}**),在欢迎页被处理的时候,这些替代符会被 **messages.properties** 文件中的信息所替代。