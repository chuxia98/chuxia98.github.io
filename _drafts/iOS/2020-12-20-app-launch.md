---
layout: post
title: App 启动优化相关
categories: iOS
---


### App 启动的三个阶段
    main() 之前

    main() 之后 main -> window.rootViewController

    首屏渲染完成 window.rootViewController -> didFinishLaunchWithOptions 执行完


### main 执行前
    * 加载可执行文件 (.o 文件)
    
    * 加载动态链接库, rebase指针调整, build 符号绑定
    
    * objc 运行时的初始化处理, 类的注册 category注册 selector 唯一性检测

    * 初始化, +load 方法, attribute 修饰的函数的调用, 创建 c++ 静态全局变量 




### 查看 APP 启动耗时
    * main() 启动耗时
    
        Product -> Scheme -> Edit Scheme -> Run -> Argumets -> Enviromment Variables 设置 DYLD_PRINT_STATISTICS = YES