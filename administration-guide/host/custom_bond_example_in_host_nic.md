# 对主机网卡使用自定义绑定选项的例子

您可以在**创建新网卡绑定**窗口中的**绑定模式**一栏中选择**自定义**来自定义网卡绑定设备。下面给出的例子您需要根据具体需要作出调整。查看[Linux Ethernet Bonding Driver HOWTO](https://www.kernel.org/doc/Documentation/networking/bonding.txt)以获得详细的网卡绑定参数列表及它们的描述。

**xmit_hash_policy**
> 此选项定义了绑定模式 2 和 4 使用的发送负载均衡策略。例如，如果您的大部分网络流量是往很多不同的 IP 地址传输的，您可能需要设置策略为根据 IP 地址进行均衡调整。您可以设置通过选择**自定义**绑定模式并输入以下内容到文本框中来设置这样的策略：
> `mode=4, xmit_hash_policy=layer2+3`

**ARP 监控**
> ARP 监控对于不能够通过 ethtool 报告链路状态的系统而言非常有用。选择*自定义*绑定模式并输入以下内容到文本框中来设置主机上网卡绑定设备的**arp\_interval** 选项：
> `mode=1, arp_interval=1, arp_ip_target=192.168.0.2`

**Primary**
> 您可能希望选择吞吐量更大的网卡作为网卡绑定设备的主网卡。选择**自定义**绑定模式并输入以下内容到文本框中来指定绑定设备的主网卡：
> `mode=1, primary=eth0`
