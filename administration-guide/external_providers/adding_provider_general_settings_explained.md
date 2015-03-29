# 添加供应商的常规设置介绍

您可以在**添加供应商**窗口中的**常规** 标签页中设置供应商的基本信息。

**添加供应商:常规设置**

|设置|解释|
|----|----|
|**名称**|在 oVirt 中代表这个供应商的名称。|
|**描述**|供应商的描述信息。|
|**类型**|供应商的类型。选择不同的供应商类型会使下面的设置有所不同。fanhang**Foreman**fanhangyouerelouai **供应商 URL**:服务商所在机器的 URL 或全称域名(FQD N)。您不需要在它的后面加端口号。splashleeelouai **要求验证**:指定是否需要验证供应商。当选择**Foreman**做为供应商类型时,必须要进行验证。splashleeelouai **用户名**:连接到 Foreman 的用户名。这个用户名必须和登录到 Foreman 上的 provisioning 门户的用户名相同。在默认的情况下,这个用户名为**admin**。splashleeelouai **密码**：以上用户验证所使用的密码。这个密码必须和登录到 Foreman 上的 provisioning portal 的密码相同。 splashleesplashyou**OpenStack 映像**fanhangyouerelouai **供应商 URL**:OpenStack 映像服务所在的机器的 URL 或全称域名(FQDN)。您需要在它的后面加端口号。默认的端口号是 9292。splashleeelouai **要求验证**:指定是否在访问 OpenStack 映像服务的时候需要验证。splashleeelouai **用户名**:连接到 OpenStack 映像服务的用户的用户名。这个用户必须是这个 OpenStack 映像服务在 Keystone 中注册的用户。默认的用户名是 **glance**。splashleeelouai **密码**: 以上用户验证所使用的密码。它必须是这个OpenStack 映像服务在 Keystone 中注册的用户的密码。splashleeelouai **Tenant Name**:OpenStack 映像服务所在的tenant 的名称。它的默认值是**Services**。splashleesplashyou**OpenStack 网络**fanhangyouerelouai **网络插件** :连接到 OpenStack 服务器的网络插件。目前用户只可以选择 Open vSwitch。splashleeelouai **供应商 URL** :OpenStack 网络服务所在的机器的 URL 或全称域名(FQDN)。您需要在它的后面加端口号。默认的端口号是 9696。splashleeelouai **用户名** :连接到 OpenStack 网络服务的用户的用户名。这个用户必须是这个 OpenStack 网络服务在 Keystone 中注册的用户。默认的用户名是 neutron。splashleeelouai **密码** : 以上用户验证所使用的密码。它必须是这个OpenStack 网络服务在 Keystone 中注册的用户的密码。splashleeelouai **Tenant Name** :OpenStack 网络服务所在的tenant 的名称。它的默认值是**Services**。splashleesplashyou|
|**测试**|测试用户所提供的验证信息。这个按钮对所有类型的供应商都有效。|
