---
title: '[EcsTest] HostDZire American'
date: 2025-08-02 17:21:29
tags:
---

## 前言
HostDZire 一家老牌的印度商家 2013年起家
看起来为LeaseWeb的分销商

我购买的是“WDC-USA Cloud VPS #1 ( Annually-Special )”
优惠码
(优惠前28.10$/yr 优惠后24$/yr≈173￥/yr) 
```
 0X5QKFWT2Q
```
买！

---

## 主观评价
最近看到这个商家一直在低价卖很高配置的印度机器，但我的生产环境和印度的网络很不适配，所以买的美国机，这个配置也算是很便宜了，于是已经抱有着超售的心态测的
但性能出乎意料的好

CPU为EPYC 单核3k多核11k，看出来可能有超售，但即使有也不多，很足够的性能

内存硬盘都很快，没有石头

网络中规中矩，需要注意的是如果谈论它回国表现的话是比较差的一档，20x的延迟，在美国机来看是算高的，但毕竟有LeaseWeb的加持，国际是很ok的
**需要提一点** 它的10g端口我测下来是至少能跑5g的，给了25Tb的流量其实非常有诚意

解锁也是中规中矩 没有很好 但至少ip定位在美国

---

## 网络拓扑
![BGPTOOLS](https://bgp.tools/pathimg/rt-207.58.128.0_18?976c8c40-53cf-4f3e-a0f0-d5b9b64e6bfa&loggedin)
## Ecs小连招测试
```
                   测评频道: https://t.me/vps_reviews                    
VPS融合怪版本：2025.07.10
Shell项目地址：https://github.com/spiritLHLS/ecs
Go项目地址 [推荐]：https://github.com/oneclickvirt/ecs
---------------------基础信息查询--感谢所有开源项目---------------------
 CPU 型号          : AMD EPYC Processor
 CPU 核心数        : 4
 CPU 频率          : 2645.028 MHz
 CPU 缓存          : L1: 128.00 KB / L2: 2.00 MB / L3: 8.00 MB
 AES-NI指令集      : ✔ Enabled
 VM-x/AMD-V支持    : ❌ Disabled
 内存              : 135.92 MiB / 5.79 GiB
 Swap              : [ no swap partition or swap file detected ]
 硬盘空间          : 1.76 GiB / 98.33 GiB
 启动盘路径        : /dev/sda1
 系统在线时间      : 0 days, 0 hour 9 min
 负载              : 0.11, 0.04, 0.01
 系统              : Debian GNU/Linux 12 (bookworm) (x86_64)
 架构              : x86_64 (64 Bit)
 内核              : 6.1.0-37-amd64
 TCP加速方式       : cubic
 虚拟化架构        : KVM
 NAT类型           : Full Cone
 IPV4 ASN          : AS30633 Leaseweb USA, Inc.
 IPV4 位置         : Washington / District of Columbia / US
----------------------CPU测试--通过sysbench测试-------------------------
 -> CPU 测试中 (Fast Mode, 1-Pass @ 5sec)
 1 线程测试(单核)得分:          3057 Scores
 4 线程测试(多核)得分:          11864 Scores
---------------------内存测试--感谢lemonbench开源-----------------------
 -> 内存测试 Test (Fast Mode, 1-Pass @ 5sec)
 单线程读测试:          34831.54 MB/s
 单线程写测试:          21466.55 MB/s
------------------磁盘dd读写测试--感谢lemonbench开源--------------------
 -> 磁盘IO测试中 (4K Block/1M Block, Direct Mode)
 测试操作               写速度                                  读速度
 100MB-4K Block         26.6 MB/s (6484 IOPS, 3.95s)            22.9 MB/s (5592 IOPS, 4.58s)
 1GB-1M Block           1.6 GB/s (1506 IOPS, 0.66s)             1.7 GB/s (1613 IOPS, 0.62s)
---------------------磁盘fio读写测试--感谢yabs开源----------------------
Block Size | 4k            (IOPS) | 64k           (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 252.57 MB/s  (63.1k) | 3.48 GB/s    (54.4k)
Write      | 253.24 MB/s  (63.3k) | 3.50 GB/s    (54.7k)
Total      | 505.82 MB/s (126.4k) | 6.99 GB/s   (109.2k)
           |                      |                     
Block Size | 512k          (IOPS) | 1m            (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 7.16 GB/s    (14.0k) | 7.68 GB/s     (7.5k)
Write      | 7.54 GB/s    (14.7k) | 8.19 GB/s     (8.0k)
Total      | 14.71 GB/s   (28.7k) | 15.88 GB/s   (15.5k)
------------流媒体解锁--基于oneclickvirt/CommonMediaTests开源-----------
以下测试的解锁地区是准确的，但是不是完整解锁的判断可能有误，这方面仅作参考使用
----------------Netflix-----------------
[IPV4]
您的出口IP完整解锁Netflix，支持非自制剧的观看
NF所识别的IP地域信息：美国
[IPV6]
您的网络可能没有正常配置IPv6，或者没有IPv6网络接入
----------------Youtube-----------------
[IPV4]
连接方式: Youtube Video Server
视频缓存节点地域: IAD(IAD23S03)
[IPV6]
Youtube在您的出口IP所在的国家不提供服务
---------------DisneyPlus---------------
[IPV4]
当前IPv4出口所在地区即将开通DisneyPlus
[IPV6]
DisneyPlus在您的出口IP所在的国家不提供服务
解锁Netflix，Youtube，DisneyPlus上面和下面进行比较，不同之处自行判断
----------------流媒体解锁--感谢RegionRestrictionCheck开源--------------
 以下为IPV4网络测试，若无IPV4网络则无输出
============[ Multination ]============
 Dazn:                                  IP Banned by Dazn
 Disney+:                               No (IP Banned By Disney+ 1)
 Netflix:                               Originals Only
 YouTube Premium:                       Yes (Region: US)
 Amazon Prime Video:                    Yes (Region: US)
 TVBAnywhere+:                          Yes
 Spotify Registration:                  Yes (Region: US)
 OneTrust Region:                       US [District of Columbia]
 iQyi Oversea Region:                   US
 Bing Region:                           US (Risky)
 Apple Region:                          US
 YouTube CDN:                           Washington DC
 Netflix Preferred CDN:                 Washington DC
 ChatGPT:                               Yes
 Google Gemini:                         Yes (Region: USA)
 Claude:                                Yes
 Wikipedia Editability:                 No
 Google Play Store:                     United States 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        USD
 ---Forum---
 Reddit:                                No
 ---Game---
 SD Gundam G Generation Eternal:        No
=======================================
 以下为IPV6网络测试，若无IPV6网络则无输出
--------------------TikTok解锁--感谢lmc999的源脚本----------------------
 Tiktok Region:         【US】
-------------IP质量检测--基于oneclickvirt/securityCheck使用-------------
数据仅作参考，不代表100%准确，如果和实际情况不一致请手动查询多个数据库比对
以下为各数据库编号，输出结果后将自带数据库来源对应的编号
ipinfo数据库  [0] | scamalytics数据库 [1] | virustotal数据库   [2] | abuseipdb数据库   [3] | ip2location数据库    [4]
ip-api数据库  [5] | ipwhois数据库     [6] | ipregistry数据库   [7] | ipdata数据库      [8] | db-ip数据库          [9]
ipapiis数据库 [A] | ipapicom数据库    [B] | bigdatacloud数据库 [C] | dkly数据库        [D] | ipqualityscore数据库 [E]
IPV4:
安全得分:
声誉(越高越好): 0 [2] 
信任得分(越高越好): 0 [8] 
VPN得分(越低越好): 100 [8] 
代理得分(越低越好): 100 [8] 
社区投票-无害: 0 [2] 
社区投票-恶意: 0 [2]
威胁得分(越低越好): 100 [8] 
欺诈得分(越低越好): 65 [E] 32 [1]
滥用得分(越低越好): 0 [3] 
ASN滥用得分(越低越好): 0.0019 (Low) [A] 
公司滥用得分(越低越好): 0.0013 (Low) [A] 
威胁级别: low [9]
黑名单记录统计:(有多少黑名单网站有记录):
无害记录数: 0 [2]  恶意记录数: 0 [2]  可疑记录数: 0 [2]  无记录数: 94 [2]  
安全信息:
使用类型: hosting - high probability [C] DataCenter/WebHosting/Transit [3] hosting [0 7 8 9 A]
公司类型: hosting [0 A] isp [7]
是否云提供商: Yes [7] 
是否数据中心: Yes [0 1 5 6 8 A C] 
是否移动设备: No [5 A C] Yes [E]
是否代理: No [0 1 4 5 6 7 8 9 A C] Yes [E]
是否VPN: No [0 1 6 7 C] Yes [A E]
是否TorExit: No [1 7] 
是否Tor出口: No [1 7] 
是否网络爬虫: No [9 A E] 
是否匿名: No [1 6 7 8] 
是否攻击者: No [7 8] 
是否滥用者: No [7 8 A C E] 
是否威胁: No [7 8 C] 
是否中继: No [0 7 8 C] 
是否Bogon: No [7 8 A C] 
是否机器人: No [E] 
DNS-黑名单: 314(Total_Check) 0(Clean) 8(Blacklisted) 20(Other) 
Google搜索可行性：NO
-------------邮件端口检测--基于oneclickvirt/portchecker开源-------------
Platform  SMTP  SMTPS POP3  POP3S IMAP  IMAPS
LocalPort ✔     ✔     ✔     ✔     ✔     ✔    
QQ        ✔     ✔     ✔     ✘     ✔     ✘    
163       ✔     ✔     ✔     ✘     ✔     ✘    
Sohu      ✔     ✔     ✔     ✘     ✔     ✘    
Yandex    ✔     ✔     ✔     ✘     ✔     ✘    
Gmail     ✔     ✔     ✘     ✘     ✘     ✘    
Outlook   ✔     ✘     ✔     ✘     ✔     ✘    
Office365 ✔     ✘     ✔     ✘     ✔     ✘    
Yahoo     ✔     ✔     ✘     ✘     ✘     ✘    
MailCOM   ✔     ✔     ✔     ✘     ✔     ✘    
MailRU    ✔     ✔     ✘     ✘     ✔     ✘    
AOL       ✔     ✔     ✘     ✘     ✘     ✘    
GMX       ✔     ✔     ✔     ✘     ✔     ✘    
Sina      ✔     ✔     ✔     ✘     ✔     ✘    
Apple     ✘     ✘     ✘     ✘     ✘     ✘    
FastMail  ✘     ✔     ✘     ✘     ✘     ✘    
ProtonMail✘     ✘     ✘     ✘     ✘     ✘    
MXRoute   ✔     ✘     ✔     ✘     ✔     ✘    
Namecrane ✔     ✔     ✔     ✘     ✔     ✘    
XYAMail   ✘     ✘     ✘     ✘     ✘     ✘    
ZohoMail  ✘     ✔     ✘     ✘     ✘     ✘    
Inbox_eu  ✔     ✔     ✔     ✘     ✘     ✘    
Free_fr   ✘     ✔     ✔     ✘     ✔     ✘    
----------------三网回程--基于oneclickvirt/backtrace开源----------------
北京电信v4 219.141.140.10  检测不到回程路由节点的IPV4地址
北京联通v4 202.106.195.68           联通4837   [普通线路] 
北京移动v4 221.179.155.161          移动CMI    [普通线路] 
上海电信v4 202.96.209.133           电信163    [普通线路] 
上海联通v4 210.22.97.1              联通4837   [普通线路] 
上海移动v4 211.136.112.200          移动CMI    [普通线路] 
广州电信v4 58.60.188.222            电信163    [普通线路] 
广州联通v4 210.21.196.6             联通4837   [普通线路] 
广州移动v4 120.196.165.24           移动CMI    [普通线路] 
成都电信v4 61.139.2.69              电信163    [普通线路] 
成都联通v4 119.6.6.6                联通4837   [普通线路] 
成都移动v4 211.137.96.205           移动CMI    [普通线路] 
准确线路自行查看详细路由，本测试结果仅作参考
同一目标地址多个线路时，可能检测已越过汇聚层，除了第一个线路外，后续信息可能无效
-----------------------回程路由--基于nexttrace开源----------------------
依次测试电信/联通/移动经过的地区及线路，核心程序来自nexttrace，请知悉!
广州电信 58.60.188.222
0.42 ms         AS30633 美国 哥伦比亚特区 华盛顿 leaseweb.com
0.37 ms         AS30633 美国 弗吉尼亚州 马纳萨斯 leaseweb.com
3.67 ms         AS30633 美国 弗吉尼亚州 马纳萨斯 leaseweb.com
1.73 ms         AS174 美国 弗吉尼亚 杜勒斯 cogentco.com
1.90 ms         AS174 [COGENT-BONE] 美国 华盛顿DC 华盛顿 cogentco.com
6.94 ms         AS174 [COGENT-BONE] 美国 纽约州 纽约 cogentco.com
15.12 ms        AS174 [COGENT-BONE] 美国 俄亥俄 克里夫兰 cogentco.com
21.78 ms        AS174 [COGENT-BONE] 美国 伊利诺伊州 芝加哥 cogentco.com
30.09 ms        AS174 [COGENT-BONE] 美国 内布拉斯加 奥马哈 cogentco.com
40.62 ms        AS174 [COGENT-BONE] 美国 科罗拉多 丹佛 cogentco.com
49.75 ms        AS174 [COGENT-BONE] 美国 犹他 盐湖城 cogentco.com
65.62 ms        AS174 [COGENT-BONE] 美国 加利福尼亚 洛杉矶 cogentco.com
66.83 ms        AS174 [COGENT-BONE] 美国 加利福尼亚 圣何塞 cogentco.com
78.17 ms        AS174 美国 加利福尼亚 圣克拉拉 cogentco.com
273.45 ms       AS4134 [CHINANET-BB] 中国 广东 广州 X-I www.chinatelecom.com.cn 电信
219.81 ms       AS4134 [CHINANET-BB] 中国 广东 广州 www.chinatelecom.com.cn
276.52 ms       AS4134 [CHINANET-GD] 中国 广东 深圳 www.chinatelecom.com.cn 电信
广州联通 210.21.196.6
0.42 ms         AS30633 美国 哥伦比亚特区 华盛顿 leaseweb.com
0.30 ms         AS30633 美国 弗吉尼亚州 马纳萨斯 leaseweb.com
4.75 ms         AS30633 美国 弗吉尼亚州 马纳萨斯 leaseweb.com
1.57 ms         AS174 美国 弗吉尼亚 杜勒斯 cogentco.com
1.92 ms         AS174 [COGENT-BONE] 美国 华盛顿DC 华盛顿 cogentco.com
18.91 ms        AS174 [COGENT-BONE] 美国 佐治亚 亚历山大 cogentco.com
25.75 ms        AS174 [COGENT-BONE] 美国 华盛顿DC 华盛顿 cogentco.com
33.72 ms        AS174 [COGENT-BONE] 美国 德克萨斯 达拉斯 cogentco.com
44.81 ms        AS174 [COGENT-BONE] 美国 得克萨斯州 埃尔帕索 cogentco.com
53.88 ms        AS174 [COGENT-BONE] 美国 亚利桑那 凤凰城 cogentco.com
63.96 ms        AS174 [COGENT-BONE] 美国 加利福尼亚 洛杉矶 cogentco.com
64.95 ms        AS174 [COGENT-BONE] 美国 加利福尼亚 洛杉矶 cogentco.com
238.61 ms       AS174 美国 加利福尼亚 洛杉矶 cogentco.com
235.53 ms       AS4837 [CU169-BACKBONE] 中国 广东 广州 chinaunicom.cn 联通
256.43 ms       AS4837 [CU169-BACKBONE] 中国 广东 广州 X-I chinaunicom.cn 联通
241.24 ms       AS17623 [APNIC-AP] 中国 广东 深圳 chinaunicom.cn 联通
259.54 ms       AS17623 中国 广东 深圳 宝安区 chinaunicom.cn 联通
广州移动 120.196.165.24
0.41 ms         AS30633 美国 哥伦比亚特区 华盛顿 leaseweb.com
0.30 ms         AS30633 美国 弗吉尼亚州 马纳萨斯 leaseweb.com
0.73 ms         AS30633 美国 弗吉尼亚州 马纳萨斯 leaseweb.com
0.97 ms         AS1299 [ARELION-NET] 美国 华盛顿哥伦比亚特区 华盛顿 arelion.com
1.52 ms         AS1299 [ARELION-NET] 美国 弗吉尼亚 阿什本 arelion.com
63.17 ms        AS1299 [ARELION-NET] 美国 佐治亚 亚历山大 arelion.com
60.68 ms        AS1299 [ARELION-NET] 美国 佐治亚 亚历山大 arelion.com
63.25 ms        AS1299 [ARELION-NET] 美国 德克萨斯 达拉斯 arelion.com
60.63 ms        AS1299 [ARELION-NET] 美国 加利福尼亚 洛杉矶 arelion.com
60.73 ms        AS1299 [ARELION-NET] 美国 加利福尼亚 洛杉矶 arelion.com
62.12 ms        AS1299 [ARELION-NET] 美国 加利福尼亚 洛杉矶 arelion.com
62.28 ms        AS58453 [CMI-INT] 美国 加利福尼亚 洛杉矶 cmi.chinamobile.com 移动
281.23 ms       AS58453 [CMI-INT] 中国 广东 广州 cmi.chinamobile.com 移动
231.13 ms       AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
235.33 ms       AS9808 [CMNET] 中国 广东 广州 I-C chinamobileltd.com 移动
293.78 ms       AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
294.24 ms       AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
243.72 ms       AS56040 [APNIC-AP] 中国 广东 深圳 gd.10086.cn 移动
--------------------自动更新测速节点列表--本脚本原创--------------------
位置             上传速度        下载速度        延迟
Speedtest.net    7419.08Mbps     5603.86Mbps     1.08ms
洛杉矶           495.33Mbps      499.32Mbps      58.04ms
法兰克福         136.27Mbps      71.82Mbps       99.34ms
联通上海         8.97 Mbps       0.00 Mbps       489.90443.00439.00
------------------------------------------------------------------------
 总共花费      : 4 分 19 秒
 时间          : Thu Jul 31 10:16:14 UTC 2025
------------------------------------------------------------------------
```