---
layout: post
title: Widget BLoC 单元测试
categories: Flutter
---

## page 页面测试 bloc 相关

```
import 'package:bloc_test/bloc_test.dart';
```

## 测试指定 state 场景

when(myBloc.state).thenReturn(MySuccess());


## BlocListener test

whenListen(
    myBloc,
    Stream.fromIterable([
        MyInitial(),
        MySuccess(),
    ]),
);

## 设置单元测试屏幕的 Size

```
tester.binding.window.physicalSizeTestValue = Size(375, 800);
tester.binding.window.devicePixelRatioTestValue = 1;
```