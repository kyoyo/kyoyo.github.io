---
layout: post
title: Git常用命令速查表
category: 常用
tags: Git
keywords: 
description: Git常用命令速查表
---

master: 默认开发分支

origin: 默认远程版本库

Head: 默认开发分支

Head^: Head的父提交

### 创建版本库

```
$ git clone <url>   #克隆远程版本库
$ git init          #初始化本地版本库
```

### 修改和提交

```
$ git status        #查看状态
$ git diff          #查看变更内容
$ git add .         #跟踪所有改动过的文件
$ git add <file>    #跟踪指定的文件
$ git mv <old><new> #文件改名
$ git rm<file>      #删除文件
$ git rm --cached<file>            #停止跟踪文件但不删除
$ git commit -m "commit messages"  #提交所有更新过的文件
$ git commit --amend               #修改最后一次改动
git checkout -- filename  #废弃工作区的修改
git log -p master.. origin/master #比较本地的仓库和远程参考的区别
git merge origin/master #把远程下载下来的代码合并到本地仓库

从远程获取最新版本到本地
git fetch origin master:temp
git diff temp
git merge temp
git branch -d temp


# 显示暂存区和工作区的差异
$ git diff

# 显示暂存区和上一个commit的差异
$ git diff --cached [file]

# 显示工作区与当前分支最新commit之间的差异
$ git diff HEAD

# 显示两次提交之间的差异
$ git diff [first-branch]...[second-branch]

# 显示今天你写了多少行代码
$ git diff --shortstat "@{0 day ago}"
```

### git diff 详细
```
git diff --stat 63bb695..cfb604d #比较两个版本  stat 内容统计
git diff --stat master  origin/master #比较本地master和远程master
git diff HEAD -- ./lib

```

### 查看提交历史

```
$ git log                    #查看提交历史
$ git log -p <file>          #查看指定文件的提交历史
$ git blame <file>           #以列表方式查看指定文件的提交历史
```

### 撤销

```
$ git reset --hard HEAD      #撤销工作目录中所有未提交文件的修改内容
$ git checkout HEAD <file>   #撤销指定的未提交文件的修改内容
$ git revert <commit>        #撤销指定的提交
$ git log --before="1 days"  #退回到之前1天的版本 
```

### 分支与标签

```
$ git branch                   #显示所有本地分支
$ git checkout <branch/tag>    #切换到指定分支和标签
$ git branch <new-branch>      #创建新分支
$ git branch -d <branch>       #删除本地分支
$ git tag                      #列出所有本地标签
$ git tag <tagname>            #基于最新提交创建标签
$ git tag -d <tagname>         #删除标签
```

### 合并与衍合

```
$ git merge <branch>        #合并指定分支到当前分支
$ git rebase <branch>       #衍合指定分支到当前分支
```
[git rebase 原理讲解](https://git-scm.com/book/zh/v1/Git-%E5%88%86%E6%94%AF-%E5%88%86%E6%94%AF%E7%9A%84%E8%A1%8D%E5%90%88)

### 远程操作

```
$ git remote -v                   #查看远程版本库信息
$ git remote show <remote>        #查看指定远程版本库信息
$ git remote add <remote> <url>   #添加远程版本库
$ git fetch <remote>              #从远程库获取代码
$ git pull <remote> <branch>      #下载代码及快速合并
$ git push <remote> <branch>      #上传代码及快速合并
$ git push <remote> :<branch/tag-name>  #删除远程分支或标签
$ git push --tags                       #上传所有标签
```



### 资料链接
1. [Try Git](https://try.github.io/levels/1/challenges/1)
2.[git回滚操作](https://github.com/geeeeeeeeek/git-recipes/wiki/5.2-%E4%BB%A3%E7%A0%81%E5%9B%9E%E6%BB%9A%EF%BC%9AReset%E3%80%81Checkout%E3%80%81Revert-%E7%9A%84%E9%80%89%E6%8B%A9)


