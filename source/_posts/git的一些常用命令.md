---
title: Git的一些实用命令
date: 2016-09-09 13:33:23
tags: [git, 随笔]
---
转眼之间我来到公司已经一个月了，回想着一个月的变化，接触的东西还是有很大的变化。比如 `git`。网上也有很多关于`git`的基础命令，比如[Chillax's blog--Git常用的基础命令](http://opiece.me/2015/04/06/git-basic-commands/)，但是我更想实例化些。下面我就把这些命令放在具体的实例当中来演示。<!--more-->
***
### 一、如何把本地的项目放到自己的远程仓库('repository')
在这个例子当中我是使用的 `github` 上的远程仓库，如果没有 `github` 的账号申请一个也是so easy.
1. 首先进入到你想要上传的项目文件夹，然后初始化：`git init`。
```
git init
```
2. 添加远程仓库，在此默认你已经在 `github` 创建了你的版本仓库，比如我的远程仓库地址是： `git@github.com:carpentercloud/testdist.git`
```
git remote add origin git@github.com:carpentercloud/testdist.git
```
3. 远程仓库已经添加好，接下来就是把本地文件上传到远程仓库
```
git add . #跟踪所有文件，别忘了add与.有个空格
git commit -m "写下你对提交的描述" #提交所跟踪的文件
ggpush #推送到远程仓库
```
***
### 二、如何在github的仓库中展示自己的项目，即 `index.html`
这里要说一下，要想在`github`上看到自己的项目展示，首先你得新建一个分支，废话不多说，还是上图来的快些
1. 点击branch，输入新的分支名字
![dd](/static/images/1.png)
2. 点击设置
![dd](/static/images/2.png)
3. 找到Github Pages,你就能看到生成的项目展示地址
![dd](/static/images/3.png)
***
### 三、Git常用的一些命令
1. 查看已有的配置信息
```
git congfig -l
```
2. 获取帮助，例如获取config命令的帮助信息
```
git help congfig
```
3. 初始化新仓库
```
git init
```
4. 跟踪文件（将文件加到暂存区）
```
git add 文件名 #具体某个文件
git add .  #跟踪全部文件
```
5. 提交更新
```
git commit -m "你的描述"
```
6. 上传/推送到仓库
```
git push origin master #推送到主分支
```
7. 从远程仓库克隆
```
git clone git@github.com:youname/project.git
```
8. 检查当前文件状态
```
git status
```
9. 创建.gitignore文件
```
touch .gitignore
```
10. 查看修改之后有没有暂存起来
```
git diff
```
11. 移除文件
```
git rm 文件名
```
12. 重命名文件
```
git mv oldname.txt newname.txt
```
13. 查看提交历史
```
git log
```
14. 取消暂存文件
```
git reset HEAD 文件名
```
15. 添加远程仓库（远程仓库已建好）
```
git remote add origin 你的远程仓库地址
```
16. 从远程仓库抓取数据
```
git fetch [remote-name]
```
17. 远程仓库的删除
```
git remote rm origin
```
18. 创建分支
```
git branch branch-name
```
19. 切换分支
```
git checkout branch-name
git checkout -b branch-name #创建并切换的该分支
```
***
* 查看所有分支
```
git branch
```
* 删除分支
```
git branch -d branch-name
git branch -D branch-name #强制删除，不会提示错误信息
```
* 合并分支
```
git merge branch-name #先切换到主分支再合并
```
***
以上基础命令参考博客地址：[Chillax's blog--Git常用的基础命令](http://opiece.me/2015/04/06/git-basic-commands/).
如果想进一步理解git可以查看：[常用 Git 命令清单](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)


***
