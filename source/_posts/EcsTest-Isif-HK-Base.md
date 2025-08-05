---
layout: '[EcsTest]'
title: Isif HongKong Base
date: 2025-08-05 05:04:40
tags:
---
## 前言
Isif 的 HongKong 基础云计算，即标题写的HK Base
最近打折了月付 80% 年付 70%
Doria的是1c1g款的，需求不大嘛，买了可能也带点吃灰

买！

---

## 主观评价
CPU 中规中矩，单核1.5k，至少不差，跟hk这个地区里的一般vps比是中上了
内存和硬盘 挺快的，特别是硬盘，虽然大文件顺序读写没有很高，但4k比一般的vps要高，最直接的体验是在shell里操作都非常跟手，看得出来没有组很多硬盘的阵列，但硬盘质量ok
IP 质量就是中下了，定位在FR，但流媒体解锁还ok
连通性 鉴于机器是HK Base，不应该对其大陆连通性提出太高的要求，国际是CTCSCI，上乘，回国到移动是Level3，所以延迟可以压低，但需要注意，走L3移动回国有较大几率被qos，下文ecs测试的末尾就可以看出来到移动能跑的带宽实际上是很低的。

*网速在国际方面是反向虚标的好评，见测评底下开启BBR后可以拉升到10Gbps左右*

点评 很高兴看见CTC系的HK落地能够降到于Hytron系相近的价格，当然还是有一定的差距，也能够理解CTC最近备受网络攻击的困难，个人觉得机器还是中规中矩。

---

## 网络拓扑
** IPV4 **
![BGPTOOLS](https://bgp.tools/pathimg/rt-151.240.13.0_24?814a88f7-403a-44b7-a3ef-7d28e56af4cf&loggedin)
** IPV6 **
![BGPTOOLS](https://bgp.tools/pathimg/rt-2405:84c0:8040::_48?eab63825-270d-4e83-86b3-58b254fd44fb&loggedin)
## Ecs小连招测试
```
                   测评频道: https://t.me/vps_reviews                    
VPS融合怪版本：2025.07.10
Shell项目地址：https://github.com/spiritLHLS/ecs
Go项目地址 [推荐]：https://github.com/oneclickvirt/ecs
---------------------基础信息查询--感谢所有开源项目---------------------
 CPU 型号          : AMD EPYC 7352 24-Core Processor
 CPU 核心数        : 1
 CPU 频率          : 2295.686 MHz
 CPU 缓存          : L1: 64.00 KB / L2: 512.00 KB / L3: 16.00 MB
 AES-NI指令集      : ✔ Enabled
 VM-x/AMD-V支持    : ✔ Enabled
 内存              : 111.71 MiB / 973.26 MiB
 Swap              : [ no swap partition or swap file detected ]
 硬盘空间          : 908.32 MiB / 19952.88 MiB
 启动盘路径        : /dev/sda1
 系统在线时间      : 0 days, 0 hour 19 min
 负载              : 0.66, 0.20, 0.07
 系统              : Debian GNU/Linux 12 (bookworm) (x86_64)
 架构              : x86_64 (64 Bit)
 内核              : 6.1.0-37-cloud-amd64
 TCP加速方式       : cubic
 虚拟化架构        : KVM
 NAT类型           : Full Cone
 IPV4 ASN          : AS209554 ISIF OU
 IPV4 位置         : Paris / Île-de-France / FR
 IPV6 位置         : China
----------------------CPU测试--通过sysbench测试-------------------------
 -> CPU 测试中 (Fast Mode, 1-Pass @ 5sec)
 1 线程测试(单核)得分:          1517 Scores
---------------------内存测试--感谢lemonbench开源-----------------------
 -> 内存测试 Test (Fast Mode, 1-Pass @ 5sec)
 单线程读测试:          39988.11 MB/s
 单线程写测试:          18203.38 MB/s
------------------磁盘dd读写测试--感谢lemonbench开源--------------------
 -> 磁盘IO测试中 (4K Block/1M Block, Direct Mode)
 测试操作               写速度                                  读速度
 100MB-4K Block         30.4 MB/s (7431 IOPS, 3.44s)            31.1 MB/s (7588 IOPS, 3.37s)
 1GB-1M Block           766 MB/s (731 IOPS, 1.37s)              779 MB/s (742 IOPS, 1.35s)
---------------------磁盘fio读写测试--感谢yabs开源----------------------
Block Size | 4k            (IOPS) | 64k           (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 48.10 MB/s   (12.0k) | 793.79 MB/s  (12.4k)
Write      | 48.14 MB/s   (12.0k) | 797.97 MB/s  (12.4k)
Total      | 96.24 MB/s   (24.0k) | 1.59 GB/s    (24.8k)
           |                      |                     
Block Size | 512k          (IOPS) | 1m            (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 2.77 GB/s     (5.4k) | 2.74 GB/s     (2.6k)
Write      | 2.92 GB/s     (5.7k) | 2.92 GB/s     (2.8k)
Total      | 5.69 GB/s    (11.1k) | 5.67 GB/s     (5.5k)
------------流媒体解锁--基于oneclickvirt/CommonMediaTests开源-----------
以下测试的解锁地区是准确的，但是不是完整解锁的判断可能有误，这方面仅作参考使用
----------------Netflix-----------------
[IPV4]
您的出口IP完整解锁Netflix，支持非自制剧的观看
NF所识别的IP地域信息：法国
[IPV6]
Netflix在您的出口IP所在的国家不提供服务
----------------Youtube-----------------
[IPV4]
连接方式: Youtube Video Server
视频缓存节点地域: 中国香港(HKG33S01)
Youtube识别地域: 中国香港(HK)
[IPV6]
连接方式: Youtube Video Server
视频缓存节点地域: IAD(IAD23S03)
---------------DisneyPlus---------------
[IPV4]
当前IPv4出口所在地区即将开通DisneyPlus
[IPV6]
当前IPv4出口所在地区即将开通DisneyPlus
解锁Netflix，Youtube，DisneyPlus上面和下面进行比较，不同之处自行判断
----------------流媒体解锁--感谢RegionRestrictionCheck开源--------------
 以下为IPV4网络测试，若无IPV4网络则无输出
============[ Multination ]============
 Dazn:                                  Yes (Region: HK)
 Disney+:                               Yes (Region: FR)
 Netflix:                               Yes (Region: FR)
 YouTube Premium:                       Yes (Region: HK)
 Amazon Prime Video:                    Yes (Region: FR)
 TVBAnywhere+:                          No
 Spotify Registration:                  Yes (Region: HK)
 OneTrust Region:                       FR [Île-de-France]
 iQyi Oversea Region:                   FR
 Bing Region:                           HK (Risky)
 Apple Region:                          FR
 YouTube CDN:                           Hong Kong
 Netflix Preferred CDN:                 Hong Kong
 ChatGPT:                               No (Only Available with Mobile APP)
 Google Gemini:                         No
 Claude:                                Yes
 Wikipedia Editability:                 Yes
 Google Play Store:                     Hong Kong 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        HKD
 ---Forum---
 Reddit:                                Yes
 ---Game---
 SD Gundam G Generation Eternal:        Yes
=======================================
 以下为IPV6网络测试，若无IPV6网络则无输出
============[ Multination ]============
 Dazn:                                  IPv6 Is Not Currently Supported
 Disney+:                               IPv6 Is Not Currently Supported
 Netflix:                               Failed (Network Connection)
 YouTube Premium:                       No
 Amazon Prime Video:                    IPv6 Is Not Currently Supported
 TVBAnywhere+:                          IPv6 Is Not Currently Supported
 Spotify Registration:                  No
 OneTrust Region:                       CN [Guangdong]
 iQyi Oversea Region:                   IPv6 Is Not Currently Supported
 Bing Region:                           CN
 Apple Region:                          CN
 YouTube CDN:                           Washington DC
 Netflix Preferred CDN:                 Failed (IP Banned By Netflix)
 ChatGPT:                               Failed (Network Connection)
 Google Gemini:                         No
 Claude:                                No
 Wikipedia Editability:                 Yes
 Google Play Store:                     China 
 Google Search CAPTCHA Free:            Yes
 Steam Currency:                        IPv6 Is Not Currently Supported
 ---Forum---
 Reddit:                                IPv6 Is Not Currently Supported
 ---Game---
 SD Gundam G Generation Eternal:        Failed (Network Connection)
=======================================
--------------------TikTok解锁--感谢lmc999的源脚本----------------------
 Tiktok Region:         Failed
-------------IP质量检测--基于oneclickvirt/securityCheck使用-------------
数据仅作参考，不代表100%准确，如果和实际情况不一致请手动查询多个数据库比对
以下为各数据库编号，输出结果后将自带数据库来源对应的编号
ipinfo数据库  [0] | scamalytics数据库 [1] | virustotal数据库   [2] | abuseipdb数据库   [3] | ip2location数据库    [4]
ip-api数据库  [5] | ipwhois数据库     [6] | ipregistry数据库   [7] | ipdata数据库      [8] | db-ip数据库          [9]
ipapiis数据库 [A] | ipapicom数据库    [B] | bigdatacloud数据库 [C] | dkly数据库        [D] | ipqualityscore数据库 [E]
IPV4:
安全得分:
声誉(越高越好): 0 [2] 
信任得分(越高越好): 5 [8]
VPN得分(越低越好): 100 [8] 
代理得分(越低越好): 100 [8] 
社区投票-无害: 0 [2] 
社区投票-恶意: 0 [2] 
威胁得分(越低越好): 85 [8] 
欺诈得分(越低越好): 92 [E] 0 [1]
滥用得分(越低越好): 0 [3] 
ASN滥用得分(越低越好): 0.0014 (Low) [A] 
公司滥用得分(越低越好): 0.0005 (Very Low) [A] 
威胁级别: low [9] 
黑名单记录统计:(有多少黑名单网站有记录):
无害记录数: 0 [2]  恶意记录数: 0 [2]  可疑记录数: 0 [2]  无记录数: 94 [2]  
安全信息:
使用类型: business [8] unknown [C] hosting [0 7 A] DataCenter/WebHosting/Transit [3] corporate [9]
公司类型: isp [7 A] 
是否云提供商: Yes [7] 
是否数据中心: Yes [0 1 A] No [5 6 8 C]
是否移动设备: No [5 A C] Yes [E]
是否代理: Yes [E] No [0 1 4 5 6 7 8 9 A C]
是否VPN: No [0 1 6 7 A C E] 
是否TorExit: No [1 7] 
是否Tor出口: No [1 7] 
是否网络爬虫: No [9 A E] 
是否匿名: No [1 6 7 8] 
是否攻击者: No [7 8] 
是否滥用者: Yes [E] No [7 8 A C]
是否威胁: No [7 8 C] 
是否中继: No [0 7 8 C] 
是否Bogon: No [7 8 A C] 
是否机器人: Yes [E] 
DNS-黑名单: 315(Total_Check) 0(Clean) 5(Blacklisted) 25(Other) 
IPV6:
安全得分:
欺诈得分(越低越好): 0 [1]
Companny滥用得分(越低越好): 0 (Very Low) [A] 
公司滥用得分(越低越好): 0 (Very Low) [A] 
安全信息:
公司类型: business [A] 
是否数据中心: Yes [1 A] 
是否移动设备: No [A] 
是否代理: No [1 A] 
是否VPN: No [1 A] 
是否TorExit: No [1] 
是否Tor出口: No [1] 
是否网络爬虫: No [A] 
是否匿名: No [1] 
是否滥用者: No [A] 
是否Bogon: No [A] 
DNS-黑名单: 315(Total_Check) 0(Clean) 0(Blacklisted) 315(Other) 
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
Apple     ✘     ✔     ✘     ✘     ✘     ✘    
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
0.14 ms         AS209554 法国 法兰西岛大区 巴黎 isif.net
0.51 ms         * RFC1918
0.52 ms         * RFC1918
0.81 ms         * RFC1918
0.55 ms         * RFC1918
0.53 ms         AS7578 中国 香港 globalsecurelayer.com
0.64 ms         AS7578 中国 香港 globalsecurelayer.com
70.61 ms        AS7578 新加坡 globalsecurelayer.com
37.75 ms        AS7578 新加坡 globalsecurelayer.com
75.27 ms        AS3356 新加坡 lumen.com
185.66 ms       AS3356 英国 lumen.com
243.38 ms       AS4134 [CHINANET-BB] 中国 广东 广州 www.chinatelecom.com.cn 电信
240.18 ms       AS4134 [CHINANET-BB] 中国 广东 广州 www.chinatelecom.com.cn
广州联通 210.21.196.6
0.12 ms         AS209554 法国 法兰西岛大区 巴黎 isif.net
0.70 ms         * RFC1918
0.71 ms         * RFC1918
0.48 ms         * RFC1918
0.49 ms         AS7578 中国 香港 globalsecurelayer.com
0.72 ms         AS7578 中国 香港 globalsecurelayer.com
70.39 ms        AS7578 新加坡 globalsecurelayer.com
37.66 ms        AS7578 新加坡 globalsecurelayer.com
70.85 ms        AS3356 新加坡 lumen.com
176.27 ms       AS3356 美国 加利福尼亚 洛杉矶 lumen.com
342.38 ms       AS3356 美国 加利福尼亚 圣何塞 Level3-CU-Peer lumen.com
* ms    AS17816 [UNICOM-GD] 中国 广东 深圳 chinaunicom.cn 联通
370.35 ms       AS17623 [APNIC-AP] 中国 广东 深圳 chinaunicom.cn 联通
348.27 ms       AS17623 中国 广东 深圳 宝安区 chinaunicom.cn 联通
广州移动 120.196.165.24
0.15 ms         AS209554 法国 法兰西岛大区 巴黎 isif.net
0.65 ms         * RFC1918
0.79 ms         * RFC1918
0.45 ms         * RFC1918
0.47 ms         AS7578 中国 香港 globalsecurelayer.com
0.50 ms         AS7578 中国 香港 globalsecurelayer.com
17.70 ms        AS3356 中国 香港 lumen.com
2.57 ms         AS3356 中国 香港 Level3-CMI-Peer lumen.com
8.78 ms         AS58453 [CMI-INT] 中国 广东 广州 cmi.chinamobile.com 移动
8.66 ms         AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
9.13 ms         AS9808 [CMNET] 中国 广东 广州 I-C chinamobileltd.com 移动
11.63 ms        AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
10.78 ms        AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
12.59 ms        AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
10.90 ms        AS56040 [APNIC-AP] 中国 广东 深圳 gd.10086.cn 移动
--------------------自动更新测速节点列表--本脚本原创--------------------
位置             上传速度        下载速度        延迟
Speedtest.net    1943.40Mbps     5539.27Mbps     853.72ms
新加坡           70.86Mbps       173.73Mbps      44.25ms
日本东京         83.81Mbps       23.34Mbps       80.94ms
联通上海5G       0.00Mbps        2.41Mbps        115.45ms
电信浙江         0.21Mbps        2.07Mbps        344.69ms
电信浙江         0.06Mbps        1.60Mbps        319.24ms
移动Chengdu      6.02Mbps        47.45Mbps       219.17ms
移动Suzhou       8.58Mbps        0.17Mbps        58.57ms
------------------------------------------------------------------------
 总共花费      : 7 分 58 秒
 时间          : Tue Aug  5 04:45:15 UTC 2025
------------------------------------------------------------------------
```

---
开启BBR后的Ookla Speedtest(即大众所熟知的 Speedtest.net )
测试端点为 MisakaNetwork Inc：Cake + [MagicTCP](https://github.com/nexstorm/magicTCP)(Doria的好朋友写的）
![图](https://youke1.picui.cn/s1/2025/08/05/689195ae0aeae.jpg)
OriginalLink https://www.speedtest.net/result/c/02475bd8-6b7f-434d-9881-bee69e4e1cfc