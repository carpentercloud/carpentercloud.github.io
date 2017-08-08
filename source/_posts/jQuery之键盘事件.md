---
title: jQuery之键盘事件
date: 2016-08-24 10:43:42
tags: [jQuery]
comments: true
categories: blog
keywords: Hexo jQuery 键盘事件
---
之所以写这个blog是应为在项目中遇到了**submit**回车提交表单的问题。想要阻止这个事件于是就搜索了一下回车事件，问题解决了，就想记录下自己的路程，用自己的语言去描述。虽然我的想法被拒绝了，还是在摸索中学到了知识(ps: 原著博客地址：[http://www.jb51.net/article/26183.htm](http://www.jb51.net/article/26183.htm)).<!-- more -->
## 一、键盘事件
首先来说下键盘事件，键盘事件分为三个事件，即按下(keydown)、释放(keyup)、敲击(keypress)

> keydown(): 事件会在键盘按下时触发
keyup(): 事件会在键盘释放时触发
keypress(): 事件会在敲击键盘时触发

而我们常用的是keypress事件。
***
## 二、获得键盘上对应的ascII码

> $(document).keypress(function(event){
  alert(event.keyCode);
});

## 三、常用键盘上对应的ascII码

> keycode 13 = Enter
keycode 37 = Left
keycode 38 = Up
keycode 39 = Right
keycode 40 = Down

## 四、我的实例
在项目中，我遇到的是表单提交之后会弹出一个成功提示，表单和提示都用的modal，而表单的submit有enter提交事件，当成功提示弹出的时候，提示modal的确定按钮没有enter事件，用户如果按enter就会不断重复提交表单数据，造成表单的重复提交。我的解决方案有两个（在项目中我们使用的是coffeeScript语法）：
### 1.在表单提交的事件当中绑定一个enter事件，return false。

> submitChange: (e)=>
    e.preventDefault()
    $(e.currentTarget).on "keypress", (e) ->
      if e.keyCode is 13 then return false
    $.ajax提交数据

这样的结果是表单的默认回车提交依然有效，在这个事件弹出的成功modal里的回车事件就会失效。bingoal！
### 2.在全局取消回车事件，return false。

> $(document).on "keypress", (e) -> if e.keyCode is 13 then return false


这样的结果是这个组件的enter事件不会有任何的反应。
