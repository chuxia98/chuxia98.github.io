---
layout: post
title: flutter中常用的命令
categories: Flutter
permalink: /command/
---

`flutter attach`
> 一般混合开发项目会用到, 原生项目启动后, 附加 flutter module 时使用

<br>

`flutter build apk`
> 打包 `Android` 时用的比较多,  apk生成路径 `项目根目录/build/app/outputs/apk`
>> 打 `Android` 渠道包时可以加一些参数: `--flavor` 渠道标识<br>
>> 默认 `release` 包, 如果需要 `Debug` 包, 跟上 `--debug` 表示 debug 包

<br>

`flutter create project_name`
 
> 创建一个新的 flutter 项目, flutter项目一般都是小写字母下划线分割, 没有特殊符号

<br>

`flutter doctor`

> 查看当前flutter版本及相关开发工具安装信息

<br>

`flutter clean`

> 清理工作区, 知情理当前项目的

<br>

`flutter devices`

> 查看当前设备

<br>

`flutter format .`

> 格式化文件 `.` 表示全部文件, 可以是单个文件

<br>


`flutter pub get`

> 修改 pubspec.yaml后, 拉依赖

<br>

`flutter upgrade`

> 更新 flutter

<br>

`flutter run`

> 运行 flutter 项目, 后面可以跟一些可选参数 
>> `-v` 启动时打印详细日志 <br>
>>`-d device-id` 运行指定的设备, `flutter device` 获取device-id <br>
>> `--release` 运行 relase 包 <br>
>> `--debug` 运行 debug 包 <br>
>> `-t main.dart` 多个启动入口 <br>
>> `--flavor daily` 不同渠道参数

<br>