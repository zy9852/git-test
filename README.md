# git-test

> 熟悉 git 命令的测试项目

## 项目中新建分支流程

1. 在项目中新建一个 issue，生成 issue 号(num)
2. 本地切到 master 分支，基于远程分支新建分支`git checkout -b num-newBranchName origin/master`
3. 将本地新分支同步到远程仓库，`git push origin num-newBranchName`
4. 当前本地已经切换至刚新建的分支，将本地分支指向远程对应的分支（防止 git push 错误）,`git branch --set-upstream-to=origin/num-newBranchName`
5. 可以开始本地正常开发

## 功能

1. [更改提交历史](editHistory.md)
