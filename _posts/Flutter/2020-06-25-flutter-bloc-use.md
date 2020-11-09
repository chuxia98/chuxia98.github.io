---
layout: post
title: Flutter BLoC 使用
categories: Flutter
---

# 简介

`BLoC` 是 `Flutter` 中状态管理的一种, 它可以实现业务逻辑与 UI 分离

其分为三部分组成 `bloc` `event` `state`

`event` 是事件类型, 所有的操作都可以看做是一个 Event事件, 比如按钮的点击, 列表的刷新, 

`state` 是处理完 `event` 对应的 `state` 状态, 比如 点击按钮后 按钮的选中或未选中, 列表的刷新状态,是在刷新中还是刷新成功/失败

`bloc` 是组织处理 `event` 返回 `state`


# 引入

在 flutter 项目中 pubspec.yaml 文件中引入 bloc

```
flutter_bloc: ^6.1.0
```

# 创建 Bloc

使用 `BlocProvider` 创建一个 bloc

```
// 中括号内是泛型, 标明当前这个 BlocProvider 是 MyBloc 类型
// 需要使用 bloc 的 widget 放在这个 BlocProvider child属性里面
BlocProvider<MyBloc>(
    create: (context) => MyBloc(),
    child: Widget(),  
),
```

使用 `BlocProvider` 创建一个 bloc



[Demo地址](https://github.com/chuxia98/flutter_demo)