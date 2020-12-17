---
layout: post
title: Flutter面试
categories: Flutter
---

### Flutter

	dart 是单线程
	
	Flutter 应用程序是多线程

		IO Runner Thread
	
		UI Runner Thread
	
		GPU Runner Thread
	
		Platform Runner Thread


### Flutter 两种编译方式

	Debug构建 `JIT` (Just In Time) 即时编译

	Release/Profile `AOT` (Ahead Of Time) 事前编译



### JNI

	dart 与 原生 交互实现

### const/final区别

### StatefulWidget 生命周期

	initState
	build
	didUpdateWidget
	didChangeDependencies
	deactivate
	dispose

    context => _element;

### StatefulWidget 触发`build`的方式

    setState()
    _element.markNeedsBuild();
    _element.owner.scheduleBuildFor(this);
    BuildOwner > onBuildScheduled();


### PlatformChannel 运行在那个县城

	BasicMessageChannel / MethodChannel / EventChannel 原理
	channel 调用是异步的
	dart 调用 channel 参数 decode 调用 c++,
	c++调用 原生
 
###	object/dynamic
	

### var 类型推导


	有初始化值, 类型推导

	```
	var type = 1;
	/// type.runtimeType = int

	type = 'String'; // 报错
	```

	没有初始化值, 类型会变

	```
	var type;

	type = 1; // int 类型
	/// type.runtimeType = int

	type = 'String'; // String 类型
	type.runtimeType = String
	```