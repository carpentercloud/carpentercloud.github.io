---
title:  content-type
date: 2017-11-30 
tags: [js,ajax]
---
今天遇到了一个很奇葩的问，就是在苹果5s下的qq浏览器，发送的post请求数据被莫名奇妙的不见了。而换成get就可以了，真是无语了。在qq自带的浏览器和其他浏览器也都正常。
<!--more-->

### 相关资料
application/x-www-form-urlencoded： 窗体数据被编码为名称/值对。这是标准的编码格式。 multipart/form-data： 窗体数据被编码为一条消息，页上的每个控件对应消息中的一个部分。 text/plain： 窗体数据以纯文本形式进行编码，其中不含任何控件或格式字符。
### 补充
form的enctype属性为编码方式，常用有两种：application/x-www-form-urlencoded和multipart/form-data，默认为application/x-www-form-urlencoded。 当action为get时候，浏览器用x-www-form-urlencoded的编码方式把form数据转换成一个字串（name1=value1&name2=value2...），然后把这个字串append到url后面，用?分割，加载这个新的url。 当action为post时候，浏览器把form数据封装到http body中，然后发送到server。 如果没有type=file的控件，用默认的application/x-www-form-urlencoded就可以了。 但是如果有type=file的话，就要用到multipart/form-data了。浏览器会把整个表单以控件为单位分割，并为每个部分加上Content-Disposition(form-data或者file),Content-Type(默认为text/plain),name(控件name)等信息，并加上分割符(boundary)。