---
title: 黑客XSS漏洞挖掘过程
date: 2017-03-31 16:08:06
tags:
---
原文[黑客漏洞挖掘](https://www.qcloud.com/community/article/172258001490259493?fromSource=gwzcw.59779.59779.59779)

### 张祖优/fooying(http://www.leiphone.com/news/201703/ivnUzjjWk20kBsrM.html)
[知乎上回答了128个关于黑客,安全的问题](http://www.leiphone.com/news/201701/Pmsr9n3y0AI3VAxR.html),研发过博彩、色情、钓鱼网站检测引擎
### Fuzzing 模糊测试
渗透测试是挖掘漏洞的最常用的手段之一，不只是XSS，Fuzzing可以用于大部分类型的漏洞挖掘。通俗可以把这种方式理解为不断尝试的过程。

![](https://blog-10039692.file.myqcloud.com/1490259301866_8855_1490259302672.jpg)
由http请求
插件初始化
解析插件配置,加载检测请求,解析用户请求,初始化进度,数据存储等
检测向量,输入入口
检测入口模块
POST,GET,COOKIE => XSS检测
潜在注入点检测 
    爬虫API,与通用方法
        * 表单检测
        * ANTI,
        * CSRF
        * WebKit解析接口
        * 爬虫Reque
    若存在潜在注入点
        循环生成XSS PayLoad
            在爬虫API与通用方法,PalyLoad攻击验证
    若不存在
        回收结果


KCon


抓bug的地方
* 知乎
* 简述
* YouPorn   almaco 查找bug事件
* Pornhub

* [黑客进军的地方](http://www.leiphone.com/news/201702/f7H0i9y7H9OOjEwm.html?ulu-rcmd=0_5021df_art_1_40ed8480-8797-4598-ae25-df54292ce35e)