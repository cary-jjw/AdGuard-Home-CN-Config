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

如果你想要指定网站走指定DNS 可以这么表达 [/baidu.com/]119.29.29.29

您也可以使用加密DNS DoH：  https://doh.pub/dns-query  https://dns.alidns.com/dns-query  或者DoT:[阿里] dns.alidns.com [腾讯]dot.pub 你可以这么写 ：tcp://dns.alidns.com 或者 udp://dns.alidns.com
再附送一个[DoH 阿里国密版本 ] https://sm2.doh.pub/dns-query  

强烈建议： DoH 模式 这也是AdGuard Home的优势。

3. 后备DNS服务器
   
   顾名思义当上游DNS故障或无法解析时候使用 ，这里建议：[腾讯]119.29.29.29  [阿里] 223.5.5.5或者填写你运营商的DNS，如果你使用的是openwrt在拨号界面应该能直接查询到。
   
4. Bootstrap  DNS服务器
   
   如果你上游服务器使用的DNS是DoH形式的 ，这里务必填写IPV4的DNS地址 ，不然AdGuard Home无法直接访问https建议：[腾讯]119.29.29.29  [阿里] 223.5.5.5

5. 私人反向 DNS 服务器

   如果你记得住IP地址对应的设备（静态IP地址设定过），可以空着不写。 但是如果你想在客户端排行不是显示IP地址，显示设备名称，那么请你填写上游IP地址（DHCP分配的路由地址）

6. DNS黑名单介绍
   
  ```
AdGuard DNS filter   https://adguardteam.github.io/HostlistsRegistry/assets/filter_1.txt
anti-AD              https://anti-ad.net/easylist.txt
秋风.top             https://raw.githubusercontent.com/TG-Twilight/AWAvenue-Ads-Rule/main/AWAvenue-Ads-Rule.txt
秋风手机             https://raw.githubusercontent.com/TG-Twilight/AWAvenue-Ads-Rule/main/Filters/AWAvenue-Ads-Rule-Replenish.txt

  ```
正常开启 AdGuard DNS filter + anti-AD  完全没有问题 。不建议使用过多的黑名单 1，网页打开会异常 2，增加系统负担。
如果你是小内存设备 建议使用 秋风 名单小，但命中率高。


==施工中==
