---
title: CSS教程 京东一 导航栏 
date: 2017-03-29 20:44:16
tags:
- CSS
category:
- CSS
- 京东
---

![](/images/step1.png)
开始之前,我们将浏览器的元素默认样式清除
style.css
```css
    * {
        margin:0;
        padding:0; 
    }
    ul{
        list-style:none;
    }
```

导航栏容器,内容居中
index.html
<script async src="//jsfiddle.net/24wings/d86gkjan/4/embed/js,html,css,result/dark/"></script>

实现 左右浮动的导航栏菜单,
将 line-height设置的和元素的height一样高,文本就会竖直居中
<script async src="//jsfiddle.net/24wings/t2bqou6m/1/embed/js,html,css,result/dark/"></script>

实现下拉菜单
index.html
style.css 
精髓是
* 默认.dropdown下只有.dt显示.dd隐藏(下拉菜单隐藏)
* 当鼠标悬停在.dropdown上,  .dd会显示
```css
.dropdown .dd{
    display:none;
}

.dropdown:hover .dd{
    display:block;
}

```
<script async src="//jsfiddle.net/24wings/5atprsh9/embed/js,html,css,result/dark/"></script>

