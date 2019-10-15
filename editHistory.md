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

## git rebase 命令

> `切记！！！如果想要改写最近提交时，必须是当前commit还没push到远程分支`

1. 更改某一次提交说明

用法：

```git
git add .
git commit -m "first commit"
// 继续开发
git add .
git commit -m "second commit"
git rebase -i HEAD~2  // HEAD~2表示修改前两次的提交

# 弹出编辑器 类似这样
# pick f7f3f6d first commit
# pick 310154e second commit
```

需要注意的是，此时弹出的编辑器显示的 commit 顺序与 git log 展示的数据是相反的。

将需要修改提交信息的 commit 信息相应的行的 pick 修改成 edit，即：

```git
edit f7f3f6d first commit
pick 310154e second commit
```

保存退出，执行`git commit --amend`，修改提交信息，再执行`git rebase --continue`就完成了对某次提交说明的更改

2. 删除或者重排提交信息

在弹出的编辑信息中，删除相应的提交行，或者更改顺序，如

```git
pick 310154e second commit
```

或者：

```git
pick 310154e second commit
pick f7f3f6d first commit
```

3. 合并提交

更改弹出的编辑信息如下：

```git
pick f7f3f6d first commit
squash 310154e second commit
```
