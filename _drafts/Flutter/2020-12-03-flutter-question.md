---
layout: post
title: Flutter面试
categories: Flutter
---

### Flutter 两种编译方式

Debug构建 `JIT` (Just In Time) 即时编译

Release/Profile `AOT` (Ahead Of Time) 事前编译

### JNI

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