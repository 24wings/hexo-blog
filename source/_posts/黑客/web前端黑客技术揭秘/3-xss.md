---
title: 3.xss
date: 2017-03-31 01:49:23
tags:
---
前端黑客之XSS
OWASP TOP10
定义: XSS即跨站脚本,发生在目标网站中目标用户的浏览器层面上,当用户浏览器渲染整个HTML文档的过程中出现了不被预期的脚本指令并执行时,XSS就会发生。

跨站脚本,引用第三方脚本
## XSS
* 反射型XSS
* 存储型XSS 放入数据库
* DOMXSS 不需要服务器解析参与,浏览器的DOM解析 `eval(location)`

常见的输入点
document.URL
document.URLUnencoded
document.location
document.referer
window.location