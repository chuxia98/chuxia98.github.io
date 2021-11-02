---
layout: post
title: Android sign
categories: Android
---

## Android空包签名相关

```
jarsigner -verbose -keystore #签名文件# -signedjar #target#.apk #source#.apk #签名别名#
```


## 查看签名文件信息

```
keytool -list -v -keystore key.keystore
```

