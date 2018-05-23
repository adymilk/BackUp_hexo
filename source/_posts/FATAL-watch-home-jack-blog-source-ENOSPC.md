---
title: FATAL watch /home/jack/blog/source/ ENOSPC
date: 2017-07-18 15:55:10
tags:
- 解决办法
categories: 代码笔记
---
最近启动`hexo` 服务的时候出现`FATAL watch /home/jack/blog/source/ ENOSPC` 这个报错导致本地服务器无法启动。 出现这个问题有几天了，百度无果。于是转到谷歌，原来是权限问题。于是我在`hexo s` 前面加了一个 `sudo` 顺利解决问题。源地址在这里 https://github.com/hexojs/hexo/issues/2013
<!-- more -->