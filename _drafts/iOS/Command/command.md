---
layout: post
title: Command
categories: iOS
---



## 命令行打包

```

xcodebuild -workspace Runner.xcworkspace -scheme universalchina -archivePath ~/Desktop/daily.xcarchive -configuration Debug archive

xcodebuild -project Runner.xcodeproj -target universalchina  -configuration  release/debug  archive -archivePath universalchina.xcarchive


xcodebuild -project "$project_name" -target "$target_name" -configuration "$configuration" -sdk iphoneos build CODE_SIGN_IDENTITY="$codeSignIdentity" PROVISIONING_PROFILE="$provision_UUID"

$ xcodebuild -project Runner.xcodeproj -target "[PROJECT_NAME]" -configuration Debug-universalchina -sdk iphoneos build CODE_SIGN_IDENTITY="$codeSignIdentity" PROVISIONING_PROFILE="$provision_UUID"

/// clean
$ xcodebuild clean -project Runner.xcodeproj -configuration ${CONFIGURATION} -alltargets

$ xcodebuild archive -project Runner.xcodeproj -scheme universalchina -archivePath ~/Desktop/Alipay.xcarchive
$ xcodebuild archive -project Runner.xcodeproj -target "[PROJECT_NAME]" 


```

### 列出可用的 scheme

xcodebuild -list 