# NAS-Foundation-101
NAS 基礎觀念 合集
  - [NAS 基礎觀念 合集](#nas-foundation-101)
  - [前言](#preface)
  - [新手採購/建構方案訣竅](#construction-tips)
  - [介紹](#introduction)
  - [常見小型網路架構](#network-enviroment)
  - [硬碟](#hard-disk-drive)
  - [磁碟陣列](#raid)  
  - [資訊安全](#information-security)
  - [Protocol](#protocol)
  - [Controller](#controller)
  - [Simulator/Emulator](#simulatoremulator)
  - [Language](#language)
  - [Library](#library)
  - [Test](#test)
  - [NFV](#nfv)
  - [Overlay Network](#overlay-network)
  - [Router](#router)
  - [Misc](#misc)
  - [High Performacne Network](#high-performance-network)
  - [Userspace Network Stack](#userspace-network-stack)
  - [Analytics](#analytics)
  - [Resources](#resources)
  - [Books](#books)
  - [Paper](#paper)  

# Preface  
NAS 實際規劃與建置 , 會遇到 網路 / 儲存體 / 伺服器應用 / 資訊安全 / 風險控管 / 災難復原 等等議題 , 本文無法涵蓋所有議題 , 因此將注意力放在 最小的必要核心概念上面 , 如果可以理解本文 , 相信就有機會開始理解 NAS 的大致樣貌 , 得到基礎的背景概念 , 進一步有能力 繼續研讀 更深入的 精彩應用 與 技術資訊 , 如果 閱讀本文讓您有點吃不消 , 可以多唸幾遍 , 回到 [NAS 社團](https://www.facebook.com/groups/nas.tw/) 請教一下其他社員 , 如果最後還是無法理解或者掌握 , 那麼 , 建議您 尋求 專業人員的協助 , 譬如 , 各家 NAS 原廠認證的 經銷商 或者 系統整合廠商 , 來為您的個人/家庭/企業組織 應用 , 做到 更為縝密以及適合的 規劃與建置目標 , 早日提升您的生活與工作效益 , 減少檔案資產的遺損風險 .  

[**-> 回到索引**](#nas-foundation-101)

# Construction Tips  
其實 , 對於任何領域來說 , 如果以 門外漢 + 業餘 來說 , 與 從業人士做對比 , 可能是 99% : 1% .

原因是 行業別太多了 , 就算只有一百種行業類別 , 要花時間專精一個領域 , 就會造成 上述的差異 . 

沒有具備基本概念 , 自行採購的情況 , 最常會發生 :
(把工程當作 3C採購)

1. 買錯設備 , 
2. 弄錯架構 , 
3. 用錯 或者 根本沒用到該發揮的功能或者效益 ,

這些其實都是 欠缺 採購前的準備所造成的 .

以 委託專業的角度來看 , 造成多元發展 是好事情 , 我們很難樣樣都自己來 , 但是 最好是在採購階段 , 個人或者採購者能具備一些 基本知識 , 才有辦法 接續著 與 該領域從業人員 , 有更適切的對談高度 , 讓 整個規劃建置執行 過程 更為順暢 以及 切合需求 , 發揮預算的最佳利用率 與 益處 .  

[**-> 回到索引**](#nas-foundation-101)

# Introduction
  NAS (網路連接儲存裝置 / 網路儲存伺服器) 為 Network Attached Storage 的縮寫.   
  一般我們會將 NAS 主機 放在 區域網路內 , 使用者可以操作電腦 , 透過內部網路存取的方式 , 取得 NAS 上的檔案或者服務資源 .   
  內部網路通常會使用到 **交換器** / **無線基地台** 等等網路設備 , 將電腦以及可連網主機或者設備連接在一起 .  
  如果需要將 內部網路 連結到 網際網路 , 會使用到 **路由器** .  
  一般家庭或者中小企業 比較常使用的其實是 路由協定包含較少 的 **IP 分享器** , 常見的用途是 [NAT(網路地址轉換)](https://zh.wikipedia.org/wiki/%E7%BD%91%E7%BB%9C%E5%9C%B0%E5%9D%80%E8%BD%AC%E6%8D%A2).  
  
  NAS 的維基百科條例 , 請參考 : [Network Attached Storage](https://zh.wikipedia.org/wiki/%E7%B6%B2%E8%B7%AF%E9%99%84%E5%8A%A0%E5%84%B2%E5%AD%98)  
  
[**-> 回到索引**](#nas-foundation-101)

# Network Enviroment
- [交換器(Switch)](https://zh.wikipedia.org/wiki/%E7%B6%B2%E8%B7%AF%E4%BA%A4%E6%8F%9B%E5%99%A8) - 擴大網路的器材，能為[子網路](https://zh.wikipedia.org/wiki/%E5%AD%90%E7%B6%B2%E8%B7%AF "子網路")中提供更多的[連接埠](https://zh.wikipedia.org/wiki/%E9%80%A3%E6%8E%A5%E5%9F%A0 "連接埠")，以便連接更多的[電腦](https://zh.wikipedia.org/wiki/%E9%9B%BB%E8%85%A6 "電腦")。.
- [無線基地台(AP)](http://www.openswitch.net) - [電腦網路](https://zh.wikipedia.org/wiki/%E9%9B%BB%E8%85%A6%E7%B6%B2%E7%B5%A1 "電腦網路")中一種連接[無線網路](https://zh.wikipedia.org/wiki/%E6%97%A0%E7%BA%BF%E7%BD%91%E7%BB%9C "無線網路")至有線網路（[乙太網](https://zh.wikipedia.org/wiki/%E4%BB%A5%E5%A4%AA%E7%BD%91 "乙太網")）的裝置.
- [路由器(Router)](https://zh.wikipedia.org/wiki/%E8%B7%AF%E7%94%B1%E5%99%A8) - 是一種[電訊](https://zh.wikipedia.org/wiki/%E9%9B%BB%E8%A8%8A "電訊")[網路](https://zh.wikipedia.org/wiki/%E7%BD%91%E7%BB%9C "網路")裝置，提供[路由](https://zh.wikipedia.org/wiki/%E8%B7%AF%E7%94%B1 "路由")與[轉送](https://zh.wikipedia.org/w/index.php?title=%E8%BD%89%E9%80%81&action=edit&redlink=1 "轉送（頁面不存在）")兩種重要機制，可以決定[封包](https://zh.wikipedia.org/wiki/%E5%B0%81%E5%8C%85 "封包")從來源端到目的端所經過的路由路徑（host到host之間的傳輸路徑），這個過程稱為路由；將路由器輸入端的封包移送至適當的路由器輸出端（在路由器內部進行），這稱為轉送。  
- [防火牆](https://zh.wikipedia.org/wiki/%E9%98%B2%E7%81%AB%E5%A2%99) - 架設在網際網路與企業內網之間的資安系統，根據企業預定的策略來監控往來的傳輸。防火牆可能是一台專屬的網路裝置或是執行於主機上來檢查各個網路介面上的網路傳輸。可以參考 [這一篇](https://www.facebook.com/groups/nas.tw/permalink/10156318392593245/) 社團文章

上述設備的組合 , 從 :
- 最基本的 數據機 <-> 電腦 , 到
- 進階一點的 數據機 <-> 路由器 (IP分享器) <-> 電腦 , 乃至於
- 完整一點的 數據機 <-> 路由器 (IP分享器) <-> 交換器 <-> 電腦 ,  

以上的簡易結構圖 , 在 [這篇文章](https://www.howtogeek.com/99001/htg-explains-routers-and-switches/) , 提供的圖解 , 畫得滿清楚的 .

**台灣常見網路設備品牌**  

--   [ASUS 華碩](https://www.asus.com/tw/Networking/) [何處購買]()
--   [Cerio 智鼎](https://www.cerio.com.tw/) [何處購買](http://buy.cerio.com.tw/content.php?id=1562)
--   [Cisco 思科](https://www.cisco.com/c/zh_tw/solutions/enterprise-networks/index.html) [何處購買](https://www.cisco.com/c/zh_tw/buy.html)
--   [D-Link 友訊](http://www.dlinktw.com.tw/) [何處購買](http://www.dlinktw.com.tw/singlepage/location)
--   [DrayTek 居易](https://www.draytek.com/zh/) [何處購買](https://www.draytek.com/zh/contact/global-partners.html)
--   [EDIMAX 訊舟](http://www.edimax.com.tw/edimax/tw/) [何處購買](http://www.edimax.com.tw/edimax/post/post/data/edimax/tw/worldwide_contact/)
--   [HUAWEI 華為](https://consumer.huawei.com/tw/) [何處購買](https://consumer.huawei.com/tw/store-finder/)
--   [NETGEAR](http://www.netbridgetech.com.tw/#) [何處購買](http://shop.netbridgetech.com.tw/netbridge/)
--   [netis](http://www.netis-systems.com.tw/) [何處購買](http://shop.netis-systems.com.tw/)
--   [SAPIDO](http://www.sapido.com.tw/TC/home.htm) [何處購買](http://www.sapido.com.tw/TC/wheretobuy01.htm)
--   [TP-LINK](https://www.tp-link.com/tw/) [何處購買](https://www.tp-link.com/tw/where-to-buy#%E7%B6%93%E9%8A%B7%E5%95%86)
--   [Tenda](https://idotcom.com.tw/product-category/3c/tenda/) [何處購買](https://idotcom.com.tw/location/)
--   [TAMIO 塔米歐](https://www.tamio.com.tw/) [何處購買](https://shop.tamio.com.tw/)
--   [TOTOLINK](https://www.totolink.tw/) [何處購買](https://www.totolink.tw/about.php?id=225)
--   [Zyxel 合勤](https://www.zyxel.com/tw/zh/homepage.shtml) [何處購買](https://www.zyxel.com/tw/zh/where_to_buy/where_to_buy.shtml).  

[**-> 回到索引**](#nas-foundation-101)

- [OcNOS](https://www.ipinfusion.com/) - Extensive switching and routing protocol support with advanced
capabilities such as MPLS and SDN
- [FlexSwitch](https://snaproute.com/) - The first open source network protocol suite offering complete layer2/layer3 functionality for accelerating development and deployment of whitebox networking gear
- [beluganos](https://github.com/beluganos/beluganos) - Beluganos is a new network OS designed for white-box switches (OF-DPA), which can apply large-scale networks.
- [SONiC](https://azure.github.io/SONiC/) - Software for Open Networking in the Cloud
SONiC


# Hard Disk Drive
- [**硬碟**](https://zh.wikipedia.org/wiki/%E7%A1%AC%E7%9B%98) - （英語：**Hard Disk Drive**，簡稱**HDD**）是[電腦](https://zh.wikipedia.org/wiki/%E7%94%B5%E8%84%91 "電腦")上使用堅硬的旋轉碟片為基礎的[非揮發性](https://zh.wikipedia.org/wiki/%E9%9D%9E%E6%8C%A5%E5%8F%91%E6%80%A7%E8%AE%B0%E5%BF%86%E4%BD%93 "非揮發性記憶體")[儲存裝置](https://zh.wikipedia.org/wiki/%E5%AD%98%E5%82%A8%E8%AE%BE%E5%A4%87 "儲存裝置")，它在平整的磁性表面儲存和檢索數字資料，資訊通過離磁性表面很近的磁頭，由電磁流來改變極性方式被電磁流寫到磁碟上，資訊可以通過相反的方式讀取，例如讀頭經過紀錄資料的上方時[磁場](https://zh.wikipedia.org/wiki/%E7%A3%81%E5%9C%BA "磁場")導致線圈中電氣訊號的改變。硬碟的讀寫是採用[隨機存取](https://zh.wikipedia.org/wiki/%E9%9A%A8%E6%A9%9F%E5%AD%98%E5%8F%96 "隨機存取")的方式，因此可以以任意順序讀取硬碟中的資料[[2]](https://zh.wikipedia.org/wiki/%E7%A1%AC%E7%9B%98#cite_note-2)。硬碟包括一至數片高速轉動的磁碟以及放在[致動器](https://zh.wikipedia.org/wiki/%E6%89%A7%E8%A1%8C%E5%99%A8 "致動器")懸臂上的磁頭。    
近年出現過的介面有 : **硬碟**按資料介面不同，大致分為[ATA](https://zh.wikipedia.org/wiki/ATA "ATA")（[IDE](https://zh.wikipedia.org/wiki/%E9%9B%86%E6%88%90%E8%AE%BE%E5%A4%87%E7%94%B5%E8%B7%AF "整合裝置電路")）和[SATA](https://zh.wikipedia.org/wiki/SATA "SATA")以及[SCSI](https://zh.wikipedia.org/wiki/SCSI "SCSI")和[SAS](https://zh.wikipedia.org/wiki/%E4%B8%B2%E5%88%97SCSI "串列SCSI")。  
目前最多數使用的是 SATA 介面 .  

[**-> 回到索引**](#nas-foundation-101)  

# RAID
[RAID (磁碟陣列)](https://zh.wikipedia.org/wiki/RAID)    

**容錯式磁碟陣列**（**RAID**,  **R**edundant  **A**rray of  **I**ndependent  **D**isks），舊稱**容錯式廉價磁碟陣列**（**R**edundant  **A**rray of  **I**nexpensive  **D**isks），簡稱**磁碟陣列**。其基本思想就是把多個相對便宜的硬碟組合起來，成為一個硬碟陣列組，使效能達到甚至超過一個價格昂貴、容量巨大的硬碟。根據選擇的版本不同，RAID比單顆硬碟有以下一個或多個方面的好處：增強資料整合度，增強容錯功能，增加處理量或容量。另外，磁碟陣列對於電腦來說，看起來就像一個單獨的硬碟或邏輯存儲單元。分為[RAID-0](https://zh.wikipedia.org/wiki/RAID#RAID_0)，[RAID-1](https://zh.wikipedia.org/wiki/RAID#RAID_1)，RAID-1E，[RAID-5](https://zh.wikipedia.org/wiki/RAID#RAID_5)，[RAID-6](https://zh.wikipedia.org/wiki/RAID#RAID_6)，RAID-7，RAID-10，RAID-50，RAID-60。(其他常見的還有 : [JBOD](https://zh.wikipedia.org/wiki/RAID#JBOD) , 以及 [RAID 10/01](https://zh.wikipedia.org/wiki/RAID#RAID_10/01))

簡單來說，RAID把多個[硬碟](https://zh.wikipedia.org/wiki/%E7%A1%AC%E7%A2%9F "硬碟")組合成為一個邏輯磁區，因此，[作業系統](https://zh.wikipedia.org/wiki/%E4%BD%9C%E6%A5%AD%E7%B3%BB%E7%B5%B1 "作業系統")只會把它當作一個硬碟。RAID常被用在[伺服器](https://zh.wikipedia.org/wiki/%E4%BC%BA%E6%9C%8D%E5%99%A8 "伺服器")電腦上，並且常使用完全相同的硬碟作為組合。    


| RAID 1  | RAID 5   |
|--|--|
|![RAID 1](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b7/RAID_1.svg/195px-RAID_1.svg.png)  | ![RAID 5](https://upload.wikimedia.org/wikipedia/commons/thumb/6/64/RAID_5.svg/330px-RAID_5.svg.png) |    

[**-> 回到索引**](#nas-foundation-101)
   

- [OpenvSwtich](http://openvswitch.org/) - Open vSwitch is a production quality, multilayer virtual switch.
- [Indigo](https://github.com/floodlight/indigo) - Indigo is an open source project aimed at enabling support for OpenFlow on physical and hypervisor switches.
- [CPqD](https://github.com/CPqD/ofsoftswitch13)- An OpenFlow 1.3 compatible user-space software switch implementation
- [Lagopus](https://lagopus.github.io) - A high-performance software OpenFlow 1.3 switch.
- [LINC-Switch](https://github.com/FlowForwarding/LINC-Switch) - A pure OpenFlow software switch written in Erlang
- [snabbswitch](https://github.com/SnabbCo/snabbswitch) - An open source virtualized Ethernet networking stack.
- [ZeroTier](https://github.com/zerotier/ZeroTierOne) - ZeroTier is a software-based managed Ethernet switch for planet Earth.
- [PISCES](http://pisces.cs.princeton.edu/) - A Programmable, Protocol-Independent Software Switch.
- [BESS](https://github.com/NetSys/bess) - Berkeley Extensible Software Switch, BESS is a modular framework for software switches.
- [FD.IO](https://fd.io/) - Relentlessly focused on data IO speed and efficiency for more flexible and scalable networks and storage

# Information Security

資訊安全 並不是 買二台 NAS 或者 買一台防火牆 這麼單純 . 更別說只有一台 NAS (或者沒有 NAS 或者任何檔案[備份](https://zh.wikipedia.org/wiki/%E5%A4%87%E4%BB%BD)機制的情況) . NAS 裡面因為有 作業系統 / 伺服器套件 / 使用者端軟體 等等的組合協助之下 , 因此比起一般 人工手動備份 , 多了許多機制以及選項 . 無論 個人 / 家庭 / 企業組織 , 都應該預先考慮 [備份 3-2-1 法則](https://www.ithome.com.tw/tech/101369) .

- [資訊安全](https://zh.wikipedia.org/wiki/%E4%BF%A1%E6%81%AF%E5%AE%89%E5%85%A8) - 為保護資訊及資訊系統免受未經授權的進入、使用、披露、破壞、修改、檢視、記錄及銷毀。

政府、軍隊、公司、金融機構、醫院、私人企業積累了大量的有關他們的雇員、顧客、產品、研究、金融資料的機密資訊。絕大多數此類的資訊現在被收集、產生、儲存在電子電腦內，並通過網路傳送到別的電腦。

萬一諸如一家企業的顧客、財政狀況、新產品線的機密資訊落入了其競爭對手的掌握，這種資安性的喪失可能會導致經濟上的損失、法律訴訟甚至該企業的破產。保護機密的資訊是商業上的需求，並且在許多情況中也是道德和法律上的需求。
- [OpenVirtex](https://github.com/opennetworkinglab/OpenVirteX) - A network hypervisor that can create multiple virtual and programmable networks on top of a single physical infrastructure.  

[**-> 回到索引**](#nas-foundation-101)

# Protocol

- [OpenFlow](https://www.opennetworking.org/sdn-resources/openflow) - A communications protocol that gives access to the forwarding plane of a network switch or router over the network.
- [OF-Config](https://www.opennetworking.org/technical-communities/areas/specification/1928-of-config) - OpenFlow Management and Configuration Protocol
- [OVSDB](https://tools.ietf.org/html/rfc7047) - A communication protocol which used to manage the OpenvSwitch database.
- [NETCONF](https://en.wikipedia.org/wiki/NETCONF)
- [OpFlex](http://www.cisco.com/c/en/us/solutions/collateral/data-center-virtualization/application-centric-infrastructure/white-paper-c11-731302.html)
- [Path Computation Element Protocol, PCEP](https://www.juniper.net/documentation/en_US/junos/topics/concept/mpls-pcep-overview.html)
- [Extensible Messaging and Presence Protocol, XMPP](https://en.wikipedia.org/wiki/XMPP)

# Controller

- [NOX](https://github.com/noxrepo/nox) - An open source development platform for C++-based software-defined networking (*SDN*) control applications.
- [POX](https://github.com/noxrepo/pox) - An open source development platform for Python-based software-defined networking (*SDN*) control applications.
- [NodeFlow](https://github.com/gaberger/NodeFLow) - An OpenFlow Controller Node Style.
- [ONOS](http://onosproject.org) - Open Network Operating System.
- [OpenDaylight](https://www.opendaylight.org) - OpenDaylight Platform
- [Ryu](https://osrg.github.io/ryu) - A component-based software defined networking framework.
- [Floodlight](https://github.com/floodlight/floodlight) - A java-based OpenFlow controller.
- [Vyatta](https://github.com/BRCDcomm/BVC/) - The first commercial Controller built directly from OpenDaylight.
- [OpenContrail](http://www.opencontrail.org/) - A SDN project that utilizes SDN & NFV and provides all the necessary components for network virtualization.
- [IRIS](http://openiris.etri.re.kr/) - A Resursive SDN Openflow Controller created by SDN Research Section, ETRI.
- [Open MUL](http://www.openmul.org/openmul-controller.html) - A lightweight SDN/Openflow controller written almost entirely in C from scratch.
- [OESS](https://github.com/globalnoc/oess) - The Open Exchange Software Suite to configure and control OpenFlow Enabled switches.
- [Beehive Network Controller](https://github.com/kandoo/beehive-netctrl) - A distributed SDN controller built on top of Beehive. It supports OpenFlow but can be easily extended for other southbound protocols.
- [Ravel](https://github.com/ravel-net/ravel) - A software-defined networking (SDN) controller that uses a standard SQL database to represent the network.
- [Trema](https://trema.github.io/trema/) - A full-stack, easy-to-use framework for developing OpenFlow controllers in Ruby and C.
- [Open Security Controller](https://www.opensecuritycontroller.org/) - Software-defined security orchestration solution that automates deployment of virtualized network security functions, like next-generation firewall, intrusion prevention systems and application data controllers
- [Netrack](https://github.com/netrack/openflow) - An OpenFlow controller framework in Go.

# Simulator/Emulator

- [Mininet](http://mininet.org/) - An Instant Virtual Network on your Laptop (or other PC)
- [OpenNet](http://github.com/dlinknctu/opennet) - A simulator for software-defined wireless local area network
- [EstiNet](http://www.estinet.com/products.php?lv1=13&sn=13) - A world-renowned software tool for network planning
- [ns-3](https://www.nsnam.org/) - A discrete-event network simulator that supports OpenFlow environment.
- [Containernet](https://github.com/containernet/containernet) - Mininet fork that allows to use Docker containers as hosts in emulated networks
- [Tinynet](https://github.com/John-Lin/tinynet) - A lightweight instant virtual network for rapid prototyping SDN
- [MaxiNet](http://maxinet.github.io) - MaxiNet extends the famous Mininet emulation environment to span the emulation across several physical machines. This allows to emulate very large software-defined networks. 

# Language

- [P4](http://p4.org/) - A declarative language for expressing how packets are processed by the pipeline of a network forwarding element such as a switch, NIC, router or network function appliance.
- [POF](https://dl.acm.org/citation.cfm?id=2491190) - Protocol Oblivious Forwarding
- [Frenetic](https://github.com/frenetic-lang/frenetic) - The Frenetic Programming Language and Runtime System
- [Pyretic](http://www.frenetic-lang.org/pyretic/) - Pyretic is one member of the Frenetic family of SDN programming languages.
- [NEMO](https://wiki.onosproject.org/display/ONOS/NEMO+Language) - A domain specific language (DSL) based on abstraction of network models and conclusion of operation patterns.

# Library

- [loxigen](https://github.com/floodlight/loxigen) - LoxiGen is a tool that generates OpenFlow protocol libraries for a number of languages.
- [openfaucet](https://github.com/rlenglet/openfaucet) - openfaucet is a pure Python implementation of the OpenFlow 1.0.0
protocol, based on Twisted.
- [oflib-node](https://github.com/TrafficLab/oflib-node) - Oflib-node is an OpenFlow protocol library for Node. It converts between OpenFlow wire protocol messages and Javascript objects.
- [OpenFlowJ](https://bitbucket.org/openflowj/openflowj) - A Java implementation of low-level OpenFlow packet marshalling/unmarshalling and IO operations.
- [nettle](https://github.com/AndreasVoellmy/openflow) - A Haskell library for working with the OpenFlow protocol.
- [OCaml OpenFlow](https://github.com/frenetic-lang/ocaml-openflow) - A serialization and protocol library for OpenFlow.
- [Scapy](http://www.secdev.org/projects/scapy/) - Scapy is a powerful interactive packet manipulation program.

# Test

- [oftest](https://github.com/floodlight/oftest) - OpenFlow Testing Framework
- [STS](https://ucb-sts.github.com/sts/) - SDN Troubleshooting System, simulates network devices, allowing programmatically test cases generation.
- [nice-of](https://code.google.com/archive/p/nice-of/) - A tool to test OpenFlow controller application for the NOX controller platform.
- [OpenSDNCore](http://www.opensdncore.org/) - Virtualisation Testbed for NFV/SDN Environment.
- [Cbenech](https://github.com/mininet/oflops/tree/master/cbench) - Benchmarking tool for controllers

# NFV

- [OPNFV](https://www.opnfv.org) - Accelerating NFV's evolution through an integrated, open platform.

# Overlay Network

- [VXLAN](https://docs.ustack.com/unp/src/architecture/vxlan.html) - Virtual Extensible LAN
- [NVGRE](https://tools.ietf.org/html/draft-sridharan-virtualization-nvgre-00) - NVGRE-Network-Virtualization-using-Generic-Routing-Encapsulation

# Router

- [FreeRouter](http://freerouter.nop.hu/) - Java-based vRouter
- [Bird](http://bird.network.cz/)
- [Quagga](http://www.quagga.net/)
- [FRRouting](https://frrouting.org/) - An IP routing protocol suite for Linux and Unix platforms which includes protocol daemons for BGP4, BGP4+, OSPFv2, OSPFv3, RIPv1, RIPv2, RIPng, PIM-SM/MSDP and LDP as well as very early support for IS-IS, EIGRP and NHRP.
- [BGPFeeder](https://projects.bytemark.co.uk/projects/bgpfeeder)
- [bgp4r](https://github.com/jesnault/bgp4r)
- [gobgp](https://github.com/osrg/gobgp)
- [yabgp](https://github.com/smartbgp/yabgp)

# Misc

- [Central Office Re-architected as a Datacenter, CORD](http://opencord.org) - Reference Implementation of a Service Delivery Platform that Provides Cloud Economies and Agility.
- [OPEN-Orchestrator Project, Open-O](https://www.open-o.org)
- [Open Source MANO Community, OSM](https://osm.etsi.org/welcome/)
- [Enhanced Controller Orchestration Management Policy, ECOMP](http://att.com/ecomp) - Operations management framework.
- [Open Network Automation Platform, ONAP](https://www.onap.org/) - Alignment of the two projects creates a harmonized and comprehensive framework for real-time, policy-driven software automation of virtual network functions that will enable software, network, IT and cloud providers and developers to rapidly create new services.
- [Mininet Spear Narmox](http://mininet.spear.narmox.com) - A online web service provides a visualization of Mininet Topology

# High Performance Network
- [DPDK](http://dpdk.org/) - DPDK is a set of libraries and drivers for fast packet processing.
It is designed to run on any processors. The first supported CPU was Intel x86 and it is now extended to IBM POWER and ARM.
- [RDMA](https://en.wikipedia.org/wiki/Remote_direct_memory_access) - Remote direct memory access (RDMA) is a direct memory access from the memory of one computer into that of another without involving either one's operating system. This permits high-throughput, low-latency networking
- [XDP](https://www.iovisor.org/technology/xdp) - XDP or eXpress Data Path provides a high performance, programmable network data path in the Linux kernel as part of the IO Visor Project.
- [ASAP2](http://www.mellanox.com/blog/2016/12/three-ways-asap2-beats-dpdk-for-cloud-and-nfv/) - The ASAP2 accelerator is built on top of eSwitch NIC hardware, and allows either the entire virtual switch, or significant portions of virtual switch or distributed virtual router (DVR) operations to be offloaded to the Mellanox NIC


# Userspace Network Stack
- [mTCP](https://github.com/eunyoung14/mtcp) - mTCP is a highly scalable user-level TCP stack for multicore systems. mTCP source code is distributed under the Modified BSD License. For more detail, please refer to the LICENSE. The license term of io_engine driver and ported applications may differ from the mTCP’s.
- [net-next-nuse](https://github.com/libos-nuse/net-next-nuse) - Network Stack in Userspace (NUSE) NUSE allows us to use Linux network stack as a library which any applications can directory use by linking the library. Each application has its own network stack so, it provides an instant virtualized environment apart from a host operating system.
- [drv-netif-dpdk](https://github.com/rumpkernel/drv-netif-dpdk) - drv-netif-dpdk is a DPDK network interface for rump kernels. The combined result is a userspace TCP/IP stack doing packet I/O via DPDK.
- [f-stack](https://github.com/F-Stack/f-stack) - F-Stack is an user space network development kit with high performance based on DPDK, FreeBSD TCP/IP stack and coroutine API.
- [yanff](https://github.com/intel-go/yanff) - YANFF is a set of libraries for creating and deploying cloud-native Network Functions (NFs). It simplifies the creation of network functions without sacrificing performance.

# Analytics
- [PNDA](http://pnda.io/) - The scalable, open source big data analytics platform for networks and services.
- [SNAS](http://www.snas.io/) - Streaming Network Analytics System (project SNAS) is a framework to collect, track and access tens of millions of routing objects (routers, peers, prefixes) in real time.
- [Apache Spot](http://spot.incubator.apache.org/) - Community-driven cybersecurity project, built from the ground up, to bring advanced analytics to all IT Telemetry data on an open, scalable platform

# Resources
## Books

- [SDN: Software Defined Networks: An Authoritative Review of Network Programmability Technologies](https://www.amazon.com/SDN-Software-Networks-Thomas-Nadeau/dp/1449342302/&tag=eltale-20)
- [圖解OpenFlow](http://www.books.com.tw/products/CN11301942)
- [重构网络-SDN架构与实现](http://www.sdnlab.com/book/18762.html)
- [深度解析SDN: 利益、战略、技术、实践](http://www.sdnlab.com/book/9470.html)
- [SDN核心技术剖析和实战指南](http://www.sdnlab.com/book/9480.html)
- [软件定义网络:SDN与OpenFlow解析](http://www.sdnlab.com/book/9473.html)
- [Network Algorithmics：An Interdisciplinary Approach to Designing Fast Networked Devices](https://doc.lagout.org/network/Network%20Algorithmics%20An%20Interdisciplinary%20Approach%20to%20Designing%20Fast%20Networked%20Devices.pdf)
- [Network Programmability and Automation Skills for the Next-Generation Network Engineer](http://shop.oreilly.com/product/0636920042082.do)
- [SDN网络指南](https://feisky.gitbooks.io/sdn/)(OpenSource Book in Chinese by Pengfei Ni)
- [DevOps for Networking](https://www.packtpub.com/networking-and-servers/devops-networking)

## Paper
- [SDN A Comprehensive Survey](https://pdfs.semanticscholar.org/d8bd/4c1e92420200bd29cb1a233bd81eb3c28bba.pdf)
- [A Guided Tour of Data-Center Networking](http://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/40404.pdf)
- [High Performance Datacenter Networks: Architectures, Algorithms, and Opportunities](https://static.googleusercontent.com/media/research.google.com/zh-TW//pubs/archive/37069.pdf)
- [Re-architecting datacenter networks and stacks for low latency and high performance](http://dl.acm.org/citation.cfm?id=3098825)

## Awesome Posts
- [VXLAN L3应用EVPN，呈现完整overlay网络](https://www.sdnlab.com/19879.html)

## Awesome Slide
- [Open Source Networking & ONAP - The Linux Foundation](https://actionweek.tmforum.org/wp-content/uploads/2017/09/TMF-Keynote-LF-Networking-ONAP-Sept-2017-vfinal.pdf)


- [FlowVisor](https://github.com/opennetworkinglab/flowvisor) - An OpenFlow controller that acts as a hypervisor/proxy between a switch and multiple controllers. Can slice multiple switches in parallel, effectively slicing a network.
- [OpenVirtex](https://github.com/opennetworkinglab/OpenVirteX) - A network hypervisor that can create multiple virtual and programmable networks on top of a single physical infrastructure.

