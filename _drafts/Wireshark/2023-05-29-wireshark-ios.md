---
layout: post
title: Wireshark
categories: Wireshark
---


## Wireshark 抓包 iPhone

### 1.获取iPhone的UDID

`$ system_profiler SPUSBDataType | grep "Serial Number:.*" | sed s#".*Serial Number: "##`

<!-- 00008101001C5D3622E0001E -->

### 2.查看已有的接口

> `$ ifconfig -l`

<!-- 
lo0 gif0 stf0 anpi2 anpi1 anpi0 en4 en5 en6 en1 en2 en3 bridge0 ap1 en0 awdl0 llw0 utun0 utun1 utun2 en7 en8 en9
 -->

`$ /Library/Apple/usr/bin/rvictl -s [DEVICE-UDID]`

> `$ rvictl -s [UDID]` # 添加网卡
> `$ rvictl -x [UDID]` # 移除网卡

# https://stackoverflow.com/questions/21559537/bash-rvictl-command-not-found-mac-book-pro-os-x-10-7-5-xcode-4-6
