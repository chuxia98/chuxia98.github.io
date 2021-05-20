
## release 分支
  1.2  2020/11
  1.3  2021/03_cn
  1.4  2021/05_cn

## iOS运行 删除pubspec.ymal 中的非china依赖

dart scripts/cli/cli.dart preProcessPubspec china


## 国际化脚本

make Makefile import_translations

./scripts/cli/translations/automation.sh import-and-generate-dart

make import_translations

## 格式化翻译代码

dartfmt -w ./localizations_sdk

## 

sed -i '.bak' "s/github.com/mirrors.tuna.tsinghua.edu.cn\/git/g" ${DIR}/ios/Podfile



## 远程 push 代码提示文件超过100M
// Git- remote:error: this exceeds GitHub file size limit of 100.00 MB

// File android/app/debug/app-debug.aab is 147.51 MB; this exceeds GitHub's file size limit of 100.00 MB

FILE-PATH 替换路径

git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch FILE-PATH" \
  --prune-empty --tag-name-filter cat -- --all