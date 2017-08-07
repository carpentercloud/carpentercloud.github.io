---
title: react实用技巧
date: 2017-03-31 21:05:55
tags: [react]
---
首先还是想先废话的讲几句react是玩意，为啥要搞它
<!--more-->
***
#### 1.dangerouslySetInnerHTML 转义html标签
```
<div dangerouslySetInnerHTML={{__html: productDetail.product.description}}/>
<div dangerouslySetInnerHTML={{__html: "<h1>这是 &middot; 测试</h1>"}}/>
```
#### 2.获取url内的参数
`this.props.location.querry.name`
其实这个可以打印下props看一下，因为有段时间不写了，一时间没有想起来。

