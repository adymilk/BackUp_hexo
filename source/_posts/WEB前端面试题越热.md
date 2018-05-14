---
title: WEB前端面试题预热
date: 2016-10-15 01:32:26
tags: 面试
categories: web
---
![](http://obl1kak28.bkt.clouddn.com/shenghuo.jpg)
### 问题分析
往往越简单的问题越能体现一个人学习功底是否扎实，src和href在html页面中太常见了吧。今天我们来分析下这个有可能面试会遇到的问题！
<!-- more -->
### 单词缩写的含义
首先，我先翻译下它们各英文缩写：
src 是source的缩写，翻译过来为资源的意思；
在HTML中通常用于把资源插入到文档当前的节点中，标签有img、script、iframe...例如
```+html
<img src="logo.png">
```
### 注意事项
注意：当浏览器解析到此元素的时候，会暂停浏览器的渲染。直到资源被加载完毕！这也是为什么要把js脚本放在底部而不是头部的原因！！
href 是HyperText reference 的缩写，翻译过来为超文本用引用的意思。 
在HTML中通常用于a标签、link标签，例如
<link rel="stylesheet" href="mystyle.css">
<a href="http://baidu.com"></a>
注意：href在引用css样式表的时候，并不会暂停浏览器的渲染。