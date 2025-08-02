---
title: '[EcsTest] FxTransit Japan Tier1'
date: 2025-08-02 15:30:40
tags:EcsTest
---
**前言**
FxTransit最近新出的机器，2c2g20g 居然有10g@10t ，很奇怪的搭配
https://fxtransit.io/index.php/store/special/tier1-20250802

优惠码
(优惠前120usd/yr 优惠后92usd/yr≈700cny/yr) 
```
20250802-289MEIXEB5
```
买！

---

**主观评价**
cpu出乎意料的好，虽然是2c，但单核可以有3.5k，加起来快7k
硬盘内存都很常规，解锁个人认为中上游（如果没有特意做dns的话确实是很优秀了）
网络的话，BgpTool上一看是Sakura才恍然大悟，那国际一定坏不到哪去，线接的很多，但有两个值得一提的点
一个是到大陆的回程出乎意料的好，毕竟是冠以"Tier1"的机器嘛，当然肯定也不能指望一直都能保持的，毕竟不是宣传重点
第二个是Ecs测试最后的网络测速，速度没测上来，不清楚是否是bbr没调的原因（Doria是开机就测，原汁原味），在文章末尾我还会附上一个Ookla Speedtest的链接，是我调了bbr之后的
**Doria的bb**
以前没有在贵论坛发过帖子，这是第一次发（自豪）
以前的Doria是经常泡在一个Telegram叫做“VPS商家评论频道”的群友，所以也会用群主的Ecs测试脚本进行测试，目前打算的是直接整个丢出来，脚本的分割线个人认为还算显眼，点评放在最前面，就当作是自己的风格了。看到论坛上大多数用的是NodeQuality脚本，带点异域风味来。

---

**网络拓扑**
![BGPTOOLS](https://bgp.tools/pathimg/rt-103.141.183.0_24?7abbd6b9-b8c6-4d7b-8f0e-650139647550&loggedin)
**Ecs小连招测试**
```
测评频道: https://t.me/vps_reviews                    
VPS融合怪版本：2025.07.10
Shell项目地址：https://github.com/spiritLHLS/ecs
Go项目地址 [推荐]：https://github.com/oneclickvirt/ecs
---------------------基础信息查询--感谢所有开源项目---------------------
 CPU 型号          : AMD EPYC 7B13 64-Core Processor
 CPU 核心数        : 2
 CPU 频率          : 2249.998 MHz
 CPU 缓存          : L1: 128.00 KB / L2: 1.00 MB / L3: 32.00 MB
 AES-NI指令集      : ✔ Enabled
 VM-x/AMD-V支持    : ✔ Enabled
 内存              : 193.53 MiB / 1.94 GiB
 Swap              : [ no swap partition or swap file detected ]
 硬盘空间          : 1.12 GiB / 19.52 GiB
 启动盘路径        : /dev/sda1
 系统在线时间      : 0 days, 0 hour 3 min
 负载              : 0.90, 0.29, 0.10
 系统              : Debian GNU/Linux 12 (bookworm) (x86_64)
 架构              : x86_64 (64 Bit)
 内核              : 6.1.0-18-cloud-amd64
 TCP加速方式       : cubic
 虚拟化架构        : KVM
 NAT类型           : Full Cone
 IPV4 ASN          : AS32135 SAKURA LTD.
 IPV4 位置         : Tokyo / Tokyo / JP
----------------------CPU测试--通过sysbench测试-------------------------
 -> CPU 测试中 (Fast Mode, 1-Pass @ 5sec)
 1 线程测试(单核)得分: 		3489 Scores
 2 线程测试(多核)得分: 		6979 Scores
---------------------内存测试--感谢lemonbench开源-----------------------
 -> 内存测试 Test (Fast Mode, 1-Pass @ 5sec)
 单线程读测试:		41552.52 MB/s
 单线程写测试:		24602.42 MB/s
------------------磁盘dd读写测试--感谢lemonbench开源--------------------
 -> 磁盘IO测试中 (4K Block/1M Block, Direct Mode)
 测试操作		写速度					读速度
 100MB-4K Block		71.9 MB/s (17.54 IOPS, 1.46s)		85.4 MB/s (20845 IOPS, 1.23s)
 1GB-1M Block		2.6 GB/s (2519 IOPS, 0.40s)		8.6 GB/s (8184 IOPS, 0.12s)
---------------------磁盘fio读写测试--感谢yabs开源----------------------
Block Size | 4k            (IOPS) | 64k           (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 225.78 MB/s  (56.4k) | 1.73 GB/s    (27.0k)
Write      | 226.38 MB/s  (56.5k) | 1.74 GB/s    (27.1k)
Total      | 452.16 MB/s (113.0k) | 3.47 GB/s    (54.2k)
           |                      |                     
Block Size | 512k          (IOPS) | 1m            (IOPS)
  ------   | ---            ----  | ----           ---- 
Read       | 2.37 GB/s     (4.6k) | 2.54 GB/s     (2.4k)
Write      | 2.50 GB/s     (4.8k) | 2.71 GB/s     (2.6k)
Total      | 4.87 GB/s     (9.5k) | 5.26 GB/s     (5.1k)
------------流媒体解锁--基于oneclickvirt/CommonMediaTests开源-----------
以下测试的解锁地区是准确的，但是不是完整解锁的判断可能有误，这方面仅作参考使用
----------------Netflix-----------------
[IPV4]
您的出口IP完整解锁Netflix，支持非自制剧的观看
NF所识别的IP地域信息：日本
[IPV6]
您的网络可能没有正常配置IPv6，或者没有IPv6网络接入
----------------Youtube-----------------
[IPV4]
连接方式: Youtube Video Server
视频缓存节点地域: 日本 东京(NRT20S05)
Youtube识别地域: 日本(JP)
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
 Dazn:					Yes (Region: JP)
 Disney+:				Yes (Region: JP)
 Netflix:				Yes (Region: JP)
 YouTube Premium:			Yes (Region: JP)
 Amazon Prime Video:			Yes (Region: JP)
 TVBAnywhere+:				Yes
 Spotify Registration:			Yes (Region: JP)
 OneTrust Region:			JP [Tokyo]
 iQyi Oversea Region:			JP
 Bing Region:				JP (Risky)
 Apple Region:				JP
 YouTube CDN:				Tokyo
 Netflix Preferred CDN:			Tokyo
 ChatGPT:				Yes
 Google Gemini:				No
 Claude:				Yes
 Wikipedia Editability:			Yes
 Google Play Store:			Japan 
 Google Search CAPTCHA Free:		Yes
 Steam Currency:			JPY
 ---Forum---
 Reddit:				Yes
 ---Game---
 SD Gundam G Generation Eternal:	Yes
=======================================
 以下为IPV6网络测试，若无IPV6网络则无输出
--------------------TikTok解锁--感谢lmc999的源脚本----------------------
 Tiktok Region:		【JP】
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
欺诈得分(越低越好): 0 [1] 93 [E]
滥用得分(越低越好): 0 [3] 
ASN滥用得分(越低越好): 0.0031 (Low) [A]
公司滥用得分(越低越好): 0 (Very Low) [A] 
威胁级别: low [9] 
黑名单记录统计:(有多少黑名单网站有记录):
无害记录数: 0 [2]  恶意记录数: 0 [2]  可疑记录数: 0 [2]  无记录数: 94 [2]  
安全信息:
使用类型: hosting [9 A] unknown [C] isp [0 7] FixedLineISP [3] business [8]
公司类型: hosting [A] business [0 7]
是否云提供商: No [7] 
是否数据中心: No [0 1 5 6 8 C] Yes [A]
是否移动设备: No [5 A C] Yes [E]
是否代理: No [0 1 4 6 7 8 9 A C] Yes [5 E]
是否VPN: No [0 1 A C] Yes [6 7 E]
是否Tor: No [0 1 3 6 7 8 A C E] 
是否Tor出口: No [1 7] 
是否网络爬虫: No [9 A E] 
是否匿名: No [1] Yes [6 7 8]
是否攻击者: No [7 8] 
是否滥用者: Yes [E] No [7 8 A C]
是否威胁: No [7 8 C] 
是否中继: No [0 7 8 C] 
是否Bogon: No [7 8 A C] 
是否机器人: No [E] 
DNS-黑名单: 315(Total_Check) 0(Clean) 6(Blacklisted) 21(Other) 
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
北京联通v4 202.106.195.68  检测不到回程路由节点的IPV4地址
北京移动v4 221.179.155.161          移动CMI    [普通线路] 
上海电信v4 202.96.209.133  检测不到回程路由节点的IPV4地址
上海联通v4 210.22.97.1              联通4837   [普通线路] 
上海移动v4 211.136.112.200 检测不到回程路由节点的IPV4地址
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
0.14 ms 	AS18464 日本 东京都 东京
0.46 ms 	* RFC1918
0.26 ms 	* RFC1918
0.57 ms 	* RFC1918
1.97 ms 	* [BBIXINTLNET] 日本
53.84 ms 	AS17676 [BBTEC] 中国 北京 softbank.jp
155.74 ms 	AS4134 [CHINANET-BB] 中国 北京 www.chinatelecom.com.cn 电信
广州联通 210.21.196.6
0.18 ms 	AS18464 日本 东京都 东京
0.53 ms 	* RFC1918
0.38 ms 	* RFC1918
0.38 ms 	* RFC1918
1.36 ms 	* [BBIXINTLNET] 日本
49.18 ms 	AS17676 [BBTEC] 中国 北京 BBTEC-CU-Peer softbank.jp
51.48 ms 	AS4837 [CU169-BACKBONE] 中国 北京 chinaunicom.cn
112.16 ms 	AS17623 [APNIC-AP] 中国 广东 深圳 chinaunicom.cn 联通
77.31 ms 	AS17623 中国 广东 深圳 宝安区 chinaunicom.cn 联通
广州移动 120.196.165.24
0.14 ms 	AS18464 日本 东京都 东京
0.51 ms 	* RFC1918
0.30 ms 	* RFC1918
0.45 ms 	* RFC1918
16.41 ms 	AS2914 日本 东京都 东京 gin.ntt.net
102.67 ms 	AS2914 [NTT-BACKBONE] 日本 东京都 东京 gin.ntt.net
64.43 ms 	AS2914 [NTT-BACKBONE] 日本 大阪府 大阪 gin.ntt.net
51.90 ms 	AS2914 [NTT-BACKBONE] 中国 香港 gin.ntt.net
52.65 ms 	AS2914 [NTT-BACKBONE] 中国 香港 gin.ntt.net
52.11 ms 	AS2914 [NTT-BACKBONE] 中国 香港 gin.ntt.net
101.62 ms 	AS2914 [NTT-GLOBAL] 中国 香港 gin.ntt.net
52.09 ms 	AS58453 [CMI-INT] 中国 香港 cmi.chinamobile.com 移动
57.86 ms 	AS58453 [CMI-INT] 中国 广东 广州 X-I cmi.chinamobile.com 移动
57.14 ms 	AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
58.01 ms 	AS9808 [CMNET] 中国 广东 广州 I-C chinamobileltd.com 移动
62.36 ms 	AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
65.76 ms 	AS9808 [CMNET] 中国 广东 广州 chinamobileltd.com 移动
66.73 ms 	AS56040 [APNIC-AP] 中国 广东 深圳 gd.10086.cn 移动
--------------------自动更新测速节点列表--本脚本原创--------------------
位置		 上传速度	 下载速度	 延迟
Speedtest.net	 4770.86Mbps	 7902.03Mbps	 895.99ms	
日本东京	 109.48Mbps	 5.72Mbps	 6.77ms	
洛杉矶		 160.20Mbps	 161.23Mbps	 107.05ms	
联通上海	 6.11 Mbps	 0.00 Mbps	 145.21140.00356.00	
------------------------------------------------------------------------
 总共花费      : 4 分 51 秒
 时间          : Sat Aug  2 13:07:22 UTC 2025
------------------------------------------------------------------------
```

---
开启BBR后的Ookla Speedtest(即大众所熟知的 Speedtest.net )
测试端点为 GSL-TYO BBR：Cake + [MagicTCP(Doria的好朋友写的)](https://github.com/nexstorm/magicTCP)
![图](https://youke1.picui.cn/s1/2025/08/02/688e176fcfc7e.jpg)
OriginalLink https://www.speedtest.net/result/c/ca63de6e-0e28-4d94-a437-6e3d3740f35f