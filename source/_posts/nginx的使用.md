---
title: nginx的使用
date: 2017-12-30 
tage: [nginx]
---
前国内各大门户网站已经部署了Nginx，如新浪、网易、腾讯等；国内几个重要的视频分享网站也部署了Nginx，如六房间、酷6等。<!--more-->新近发现Nginx 技术在国内日趋火热，越来越多的网站开始部署Nginx。相比apeach、iis，nginx以轻量级、高性能、稳定、配置简单、资源占用少等优势广受欢迎。
***
然而这些并用不到，作为前端，用的最多的也就是在本地跑起项目，做一些映射、代理服务。
以前在mac上都是命令行搞定，而如今却转为windows用户，还是不得不来习惯性window下的命令的。
## 一、 首先安装，自然是去官网下载
地址：http://nginx.org
## 二、使用
关于使用还是比较推荐敲命令的方式来搞了，毕竟装逼一下也是好的，更主要是觉得每次去双击exe，很傻逼，好像也有弊端，比如 `这样会导致修改配置后重启、停止nginx无效，需要手动关闭任务管理器内的所有nginx进程`.
首先还是要先进入到安装nginx的目录，
> cd nginx 目录

然后
```
start nginx  //启动nginx
nginx -s reload // 修改配置后重新加载生效
nginx -s reopen // 重新打开日志文件
nginx -t -c /path/to/nginx.conf  //测试nginx配置文件是否正确

nginx -s stop // 快速停止nginx
nginx -s quit // 完整有序的停止nginx
```

`备注：`本来我是习惯用git工具的，所以在git的敲这些命令无效，转为cmd自带的命令行工具。
git里敲的是linux命令。

## 三、配置
像我这种喜欢先使用，而后才会进一步去想如果配置的，不知是否本末倒置了。
```
 http {
     gzip  on;
    #静态文件
    server {
        listen       80;
        server_name  static.cnblog.com;
        location / {
            root   G:/source/static_cnblog_com;
        }
    }
    #html文件
    server {
        listen       80;
        server_name  127.0.0.1 localhost;
        location / {
            root   G:/source/html/mobile/dist;
            index  index.html index.htm;
        }
    }
}
```