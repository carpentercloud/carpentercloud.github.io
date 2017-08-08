---
title: Hexo常用命令
date: 2016-09-02 15:54:55
tags: [Hexo]
---
前段时间好不容易弄好了自己的hexo，没想到没过多久，基础命令忘的差不多了，少不了又是一番baidu。看到一篇挺不错的关于Hexo常用命令的文章。于是干脆自己敲出来，即可以加深印象，也<!--more-->可以充下门面吧。原著地址：[hexo常用命令笔记](https://segmentfault.com/a/1190000002632530).
***
### hexo
```
npm install hexo -g #安装
npm update hexo -g #升级
hexo init #初始化
```
***
### 简写
```
hexo n "我的博客" == hexo new "我的博客" #新建文章
hexo p == hexo publish
hexo g == hexo generate #生成
hexo s == hexo server #启动服务预览
hexo d == hexo deploy #部署到。。
```
***
### 服务器
```
hexo server #Hexo 会监事文件变动并自动更新，无需重启服务器
hexo server s #静态模式
hexo server -p 5000 #更改端口

hexo clean #清除缓存
hexo g #生成静态文件
hexo d #开始部署

```

    安装RSS插件
> npm install hexo-generator-feed --save

    开启RSS功能：编辑hexo/_config.yml，添加如下代码
> rss: /atom.xml #rss地址  默认即可





***

