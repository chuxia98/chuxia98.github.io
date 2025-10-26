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

	HotReload HotRestart

	Debug构建 `JIT` (Just In Time) 即时编译

	Release/Profile `AOT` (Ahead Of Time) 事前编译



### JNI

	dart 与 原生 交互实现

### const/final区别

	都是用于声明变量的关键字，它们在变量的可变性和初始化时机上存在差异

	final

	> 用法：用于声明只能被赋值一次的变量，类型可以省略，Dart 会根据赋值自动推断类型。
	> 可变性：final 声明的变量在初始化后不可再被赋值，但如果其值是一个对象，对象的内部状态（属性）是可以改变的。
	> 初始化时机：final 变量在运行时第一次使用时被初始化。

	const

	> 用法：用于声明编译时常量，表示在编译期间即能确定的值
	> 可变性：const 声明的变量是不可变的，且其值在编译时就确定，整个对象及其内部状态都是不可变的
	> 初始化时机：const 变量在编译时被初始化，必须在声明时赋值，且赋值内容必须是编译时常量。

	final 与 const 的区别

	初始化时机：final 变量在运行时第一次使用时被初始化，而 const 变量在编译时被初始化。
	使用场景：final 适用于值在运行时确定且不会再改变的变量；const 适用于在编译时就能确定值的常量。

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


### PlatformChannel 运行在那个线程
	在 Flutter 中，Platform Channel 用于在 Dart 代码与平台（如 Android 或 iOS）之间进行通信。在平台端，Platform Channel 的代码运行在平台的主线程上。因此，处理耗时操作时，应避免在平台的主线程中执行，以防止阻塞主线程，影响应用的响应性。

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