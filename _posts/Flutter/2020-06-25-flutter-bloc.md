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
equatable: ^1.2.5
```

# 创建 Bloc

在创建`bloc`之前, 如果还没影想好会触发哪些 `event` 和 `state` 先不用着急, 可以先只写一个抽象类

`Equatable` 是 `compare objects` 的抽象类, 在 `bloc` 中用来对比 state 是否是同一个

`Bloc` 的创建都是固定的写法, VS/AS 都提供有快捷生成的命令

```
abstract class MyEvent extends Equatable {}

// 在这里创建一个 MyTitleChanged 继承 MyEvent
class MyTitleChanged extends MyEvent {
  final String title;

  MyTitleChanged({
    this.title,
  });

  @override
  List<Object> get props => [title];
}
```

```
abstract class MyState extends Equatable {
  @override
  List<Object> get props => [];
}

// 每个`bloc`都有一个初始化状态
class MyInitial extends MyState {}

// 对应 MyTitleChanged 事件的状态
class MyTitleChangeSuccess extends MyState {
  final String title;

  MyTitleChangeSuccess({
    this.title = '',
  });

  @override
  List<Object> get props => [title];
}

```

```
// 实现一个自己的`bloc`继承自`Bloc`声明是触发`MyEvent`类型的事件, 返回`MyState`类型的状态
// `Bloc` 6.0 以后必须实现的两个方法
class MyBloc extends Bloc<MyEvent, MyState> {
  // 初始化
  MyBloc() : super(MyInitial());
  
  // 触发 MyTitleChanged 事件时, 做的处理并且返回 MyTitleChangeSuccess 类型的状态
  @override
  Stream<MyState> mapEventToState(MyEvent event) async* {
    if (event is MyTitleChanged) {
      // 在这里做一些逻辑事件
      yield MyTitleChangeSuccess(title: event.title);
    }
  }
}
```

使用 `BlocProvider` 创建一个 bloc

```
// 中括号内是泛型, 标明当前这个 BlocProvider 是 MyBloc 类型
// 在当前 widget 树下可以通过 BlocProvider.of<MyBloc>(context) 取出 MyBloc 并使用
// 需要使用 bloc 的 widget 放在这个 BlocProvider child属性里面
BlocProvider<MyBloc>(
    create: (context) => MyBloc(),
    child: Widget(),  
),
```




[Demo地址](https://github.com/chuxia98/flutter_demo)