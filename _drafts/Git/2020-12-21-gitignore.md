---
layout: post
title: Git
categories: git
---


### .gitignore 生效

```
git rm -r --cached .
git add .
git commit -m 'update .gitignore'
```

### git tag

添加`tag`

```
$ git tag -a v1.4 -m "my version 1.4"
$ git tag
v0.1
v1.3
v1.4
```

删除`tag`

```
$ git tag -d v1.4
Deleted tag 'v1.4-lw' 

```



### git worktree

git worktree add ../dir branchName
git worktree remove branchName


### git archive

git archive --format tar.gz --output "./output.tar.gz" master