---
layout: post
title: Ionic install
categories: Ionic
---


[ionic](https://ionicframework.com/docs/)

### install nvm

```
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```

### install ionic

ionic need Node.js

```
// uninstall previous version
npm uninstall -g ionic
// install new version
npm install -g @ionic/cli
```

### create ionic app
```
ionic start
```

### run ionic app
```
ionic serve
```