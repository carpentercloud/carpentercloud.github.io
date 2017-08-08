---
title: meta的一些用法
date: 2017-08-08 16:30:03
tags: [js]
---
写html head的时候以前都是基本忽略其他,meta用的最多的也就是定义用什么样的编码格式，另外还要一些不太熟悉的选项，接下来列举一下，有漏掉的欢迎来补充。
<!---more-->
***
## 一、语法
`<meta name="name" content="string">`
参数解析：<br>
a. name 项：常用的选项有keywords、description、author、robots等
b. http-equiv项：可用于代替name项，畅游的选项有Expires，Pragma，Refresh，Set-Cookie(cookie设定)，Window-target(显示窗口的设定)，content-Type(显示字符集的设定)等。
c. content 项：根据name项或http-equiv项的定义来决定此项些什么样的字符串。
## 二、应用
a、告诉浏览器网页所识别的文件类型及语言类型，比如说，我们要让浏览器识别HTM/HTML类型的简体中文网面，我们可以这样写： 
<meta http-equiv="Content-Type" content="text/html; charset=gb2312" /> 
b、让一些搜索引擎搜索到你的网页，代码可以这样写： 
<meta name="keywords" content="网页关键字" /> 
<meta name="description" content="网页描述文字" /> 
要达到自动搜索引擎真正能方便地搜索到你的网页还得注意以下几点： 
1、既要定义meta标记项，又要将首页正文的前200个字符定义成反映主页主题的文字。因为有些导航台在标引meta项中的关键词的同时，还要标引正文中的前200个字符。如：altavista。所以，有些人在注册完导航台后去检查注册结果时，发现导航台中的描述并不是你所希望的，而是诸如版权说明之类的文字。产生这一现象的原因就是没有注意到这一点。 
2、将定义关键词的meta标记项放在定义描述的meta项之前。如：
``` 
<meta type="keywords" content=".......,...,..."/> 
<meta type="description" content="...,....,..."/> 
```
3、将最重要的关键词放在最前面，让相关的关键词相邻。全小写与首字母大写并存，因为有的导航台在标引时对字符的大小写是敏感的。包括标点符号不要超过250个单词 
4、首页最好不用frame结构，因为frame将屏幕划分成多个窗口后，导航台不能智能地选择正确的窗口中的主页去标引。 
c、让一个页面过上一定的时间，自动转到另一个页面或者站点去，如： 
```
<meta http-equiv="refresh" content="6; url=http://hi.baidu.com/tesalo/" /> 
```
content中的6表示时间，单位为秒，url=后面是你要转向的网址，若是与你当前网页在同一目录下，可以直接写上文件名，如：
``` 
<meta http-equiv="refresh" content="6; url=page1.htm" /> 
```
d、让网页每隔一段时间刷新一次，若要10秒刷新一次，代码这样写： 
```
<meta http-equiv="refresh" content="10"> 
```
e、通过Meta可以让你进入页面时产生一些特殊效果，具体应用如下： 
```
<meta http-equiv="Page-Enter" content= "revealTrans(Duration=5.0,Transition=n)" /> 
```
其中，n的取值范围为0-23，具体的意义如下： 
0 矩形缩小 1 矩形扩大 2 圆形缩小 3 圆形扩大 4 下到上
