

## 删除pubspec.ymal 中的非china依赖

dart scripts/cli/cli.dart preProcessPubspec china

## 

sed -i '.bak' "s/github.com/mirrors.tuna.tsinghua.edu.cn\/git/g" ${DIR}/ios/Podfile



## 远程 push 代码提示文件超过100M
// Git- remote:error: this exceeds GitHub file size limit of 100.00 MB

// File android/app/debug/app-debug.aab is 147.51 MB; this exceeds GitHub's file size limit of 100.00 MB

FILE-PATH 替换路径

git filter-branch --force --index-filter \
  "git rm --cached --ignore-unmatch FILE-PATH" \
  --prune-empty --tag-name-filter cat -- --all