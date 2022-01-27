
---
layout: post
title: Wireshark
categories: Wireshark
---



`ip.addr == 119.75.217.26 and icmp` 表示只显示ICPM协议且源主机IP或者目的主机IP为119.75.217.26的数据包


### IP 筛选

<br>

* 源地址筛选 `ip.src==192.168.1.1 `

* 目的地址筛选 `ip.dst==192.168.1.1`


![Protocol fillter](/assets/images/wireshark/1.png)

ip==xxx.xxx.xxx.xxx 是用于筛选源地址和目的地址都是该ip的包

<br>

### 协议筛选

我们想要筛选比如tcp、udp、http等相关协议的包

![Protocol fillter](/assets/images/wireshark/2.png)


### 端口和方法

#### 端口

`tcp.srcport==80`

`tcp.dstport==53379`

![Protocol fillter](/assets/images/wireshark/3.png)

`tcp.port==80` 是源端口或目的端口是80的tcp数据包

![Protocol fillter](/assets/images/wireshark/4.png)


#### 方法

方法就是指协议里面的一些方法，测试了http的GET、PUT等这些方法

`http.request.method=="GET"`

![Protocol fillter](/assets/images/wireshark/5.png)