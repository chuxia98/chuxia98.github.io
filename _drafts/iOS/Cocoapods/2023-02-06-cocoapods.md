


# 检测 trunk
pod trunk me

# 注册
pod trunk register example@qq.com "[name]" --verbose

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

# set url
git remote set-url origin https://xx@github.com/chuxia98/demo.git/
git remote set-url origin https://xxx@github.com/[author]/demoPodProject.git/

# 列出 origin url
git remote -v

pod spec lint --allow-warnings

# error

`remote: Support for password authentication was removed on August 13, 2021`

将 `podspec` 中 s.source git 替换为 SSH


pod repo push REPO [NAME.podspec]

pod trunk push [NAME.podspec] --allow-warnings