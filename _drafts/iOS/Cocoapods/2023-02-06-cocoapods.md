


# 检测 trunk
pod trunk me

# 注册
pod trunk register 875390797@qq.com "chuxia98" --verbose

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

# set url
git remote set-url origin https://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@github.com/chuxia98/OFESDK.git/
git remote set-url origin https://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@github.com/xiaYingwudi/demoPodProject.git/

# 列出 origin url
git remote -v

pod spec lint --allow-warnings

# error

`remote: Support for password authentication was removed on August 13, 2021`

将 `podspec` 中 s.source git 替换为 SSH


pod repo push REPO [NAME.podspec]

pod trunk push [NAME.podspec] --allow-warnings