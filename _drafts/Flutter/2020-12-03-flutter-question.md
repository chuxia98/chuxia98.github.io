---
layout: post
title: Flutter面试
categories: Flutter
---

Debug构建 `JIT` (just in time)
Release/Profile `AOT` (Ahead of time)

const/final区别

StatefulWidget 生命周期
	initState
	build
	didUpdateWidget
	didChangeDependencies
	deactivate
	dispose

    context => _element;
StatefulWidget 触发`build`的方式
    setState()
    _element.markNeedsBuild();
    _element.owner.scheduleBuildFor(this);
    BuildOwner > onBuildScheduled();