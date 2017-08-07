---
title: 初尝vue的味道
date: 2016-09-09 16:30:03
tags: [vue]
---
vue最近很🔥的一个前端开发开发框架，尤其和node.js的配合，更是如虎添翼。现在就我个人最近一段时间的摸索尝试来总结下我的个人经验。
<!---more-->
***
如果想学习比较系统的可以去[vue.js官网](http://cn.vuejs.org)。我用框架的想法是要构建大型的应用，能够组件化开发，架构起来方便。记得第一次看vue教程的时候并没用安装任何环境，只是像引入`jQuery`那样，虽然也实现了简单的数据双向绑定，但是怎么都感觉不过瘾。直到 我电脑上都装好了node、git等环境，又一次唤起了我尝试vue的想法。
### 一、安装命令行工具
Vue.js 提供一个官方命令行工具，可用于快速搭建大型单页应用。该工具提供开箱即用的构建工具配置，带来现代化的前端开发流程。只需一分钟即可启动带热重载、保存时静态检查以及可用于生产环境的构建配置的项目。我的目标是构建一个项目，所以这个是不可少的。
```
# 全局安装vue-cli
npm install -g vue-cli
# 创建一个基于“webpack” 模板的新项目
vue init webpack my-project
# 安装依赖，走你
cd my-project
npm install
npm run dev
```
1. `npm install`在安装依赖的过程比较会漫长，除尝者需要耐心等待下。
2. `npm run dev` 这一行命令代表着它会去找到package.json的scripts对象，执行node bulid/dev-server.js。在这文件里，配置了Webpack，会让它去编译项目文件，并且运行服务器,运行之后在8080端口即可访问到项目的首页。
vue-cli，快速构建项目工具。
***
***
一个月马上就过去了，本来月初写的，结果到了月末还没写完，真是忏愧。现在都没有当时刚用完的感悟了。这个月也基本上没在用vue了，而是在弄node.js express mongodb 了。现在都不知道怎么完结这篇博客了，那就把我学习参考的[教程](https://github.com/MeCKodo/vue-tutorial)，以及我在github的[演示demo](https://carpentercloud.github.io/testdist/#!/home)放上。
***
## 反思
这篇博客的烂尾对我来说很不舒服，但我还是把他发布了，作为以后对自己的提醒吧！不能在犯拖延症的毛病了，想起来就去干，just do it !马上就到金秋十月了，在这里给自己十月份定下个计划，继续耕读高程三的同时，要自己尝试写一些小插件。启发来自拜读了大豹的文章[《前端自学路线之js篇》](http://mp.weixin.qq.com/s?__biz=MjM5MTA1MjAxMQ==&mid=2651222700&idx=1&sn=927bb7c7ecb26c400902cdc06dc6dc5e&mpshare=1&scene=1&srcid=0930pOdaSrvsCYKdO6B84Z2b#rd)。好了，这篇blog就到此为止了，💪，frighting！
***
