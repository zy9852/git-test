# 重写历史

## git commit --amend 命令

此命令用于合并提交以及改提交信息，`但是切记！！！如果想要改写最近提交时，必须是当前commit还没push到远程分支`！

只能用于本地开发还没 push 时，用法：

```git
git add .
git commit -m "第一次提交"
// 继续开发
git add .
git commit --amend
// 唤起编辑器，修改commit message为“修改后的提交信息”
git log
// 本地仓库只有一个commit，但是包含了两次提交的内容

```
