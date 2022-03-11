---
layout: post
title: Archetype
categories: AEM
---


# AEM  Adobe Experience Manager

AEM Project Archetype

[Github](https://github.com/adobe/aem-project-archetype)

依赖 mvn(maven) npm node


生成 AEM 项目

```
mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
 -D archetypeGroupId=com.adobe.aem \
 -D archetypeArtifactId=aem-project-archetype \
 -D archetypeVersion=35\
 -D appTitle="My Site" \
 -D appId="mysite" \
 -D groupId="com.mysite"
```


部署 AEM

mvn clean install -PautoInstallSinglePackage


需要安装启动 AEM



