---
title: node相关的一些常用命令
date: 2017-03-10 14:02:33
tags: [Node,nvm]
---
最近遇到node频繁更新，与项目中herd版本有依赖，遇到一些坑，也就用到了一些关于node的一些管理工具nvm(用了window才知道这只是mac下能用的，坑，windows下就别想了)，下面就来先说一下nvm吧<!--more-->
***
### 一、node相关的一些命令
```
使用默认的node版本：nvm alias default 7.5.0
临时使用node版本： nvm use 7.5
安装node最新版本号： nvm install node
安装node指定版本： nvm install 7.5.0
安装herd 指定版本： npm i @terminus.herd@0.4.4

```
### 二、 node升级


## 全局安装cnpm
`npm install -g cnpm --registry.npm.taobao.org`
先是装cnpm 淘宝镜像不成功
node 6.10.3
npm 3.10
然后才想着升级node
正如大多数说的那样，首先安装n
npm install -g n
升级node.js到最新稳定版
n stable
但是没卵用，这是在mac下的。
好不容易已找到了win10下的 npm install -g --force
可是到了下一步又， 报无效的版本。
也是够了，索性去官网重新下载安装包，简单省事。


`1.npm putdated 列出已过时的抱`
`2.npm update 更新模块`
`2.npm list node-sass 列出安装模块的信息`

## windows 下 ERROR in Node Sass does not yet support  your current environmen


Module build failed: Error: Node Sass does not yet support your current environment: Windows 64-bit with Unsupported runtime (57)
(G:\work\sdwActivity\node_modules\_node-sass@3.13.1@node-sass\lib\binding.js:13:13)
明明已经安装了最新的node-sass，并且官网也查了，4.7.2版本的node-sass支持 windows 64-bit node8 ，却发现报的还是node-sass3.13.1 ，坑，竟然安装了两个node-sass，默认使用了3.13版
npm node-sass 安装最新版本sass无效，查看安装的node-sass版本号，先删除node-moudle文件，再node

