![image](https://github.com/user-attachments/assets/db6d9af0-0862-4fc0-84d9-a360c3031aa2)

**1. 配置前准备工作**
由于网络配置环境有别 ，建议在配置前（非部署AdGuard Home环境）利用 https://www.dnsip.cn/ 进行DNS测速。
建议多测试几次按均值记录。另外 https://www.dnsip.cn/ 测试是是基于IPV4 DNS 如果是要配置DOT DOH 就没有关系了

**2. AdGuard Home 设置- DNS设置**
依据以上测试结果进行DNS填写，不过几个大厂的DNS，罗列几个大家可以参加。

2.1主流DNS
  
```
腾讯 ：119.29.29.29
阿里 ：223.5.5.5
百度： 122.112.208.1
```
  

当然AdGuard Home默认IPV4 DNS是UDP模式，你也可以这样写：

```
udp://119.29.29.29
udp://223.5.5.5
udp://122.112.208.1
```

如果是你想要TCP模式 ，例如：tcp://119.29.29.29
