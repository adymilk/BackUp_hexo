---
title: hexo同步到github时免输入用户名密码
date: 2016-10-01 23:23:31
tags: 
- hexo
- 博客
categories: 代码笔记
---
![](http://p1.bqimg.com/567571/6c03834cfd169383.png)
hexo 每次同步代码到github都需要手动输入用户名和密码确实挺烦人的，下面给出解决办法......
<!-- more -->
### 第一种方案
#### 两部走
1、新建系统环境变量，变量名：%USERPROFILE% 变量值：%USERPROFILE% 如下图
![](http://i1.piimg.com/567571/4c48e02296a29deb.png)
2、在目录(C:\Users\你电脑的用户名) 下新建文件名为`_netrc`的文件，编辑以下内容
```
machine github.com
login 你github用户名
password 你github的密码
```
#### 保存退出

> 转自[foreverpx的博客](http://blog.csdn.net/forevercjl/article/details/39557713)

### 第二种方案
如果第一种方案失效，请参考下面这个方法
#### 配置站点的`_config.yml`文件，修改或添加`repository`值为ssh地址。`_config.yml`配置如下图
```
##ssh地址来源于项目的clone with ssh
deploy:
  type: git
  repository: git@github.com:adymilk/adymilk.github.io.git
  branch: master
```
#### 保存重新部署到github
```
$hexo d
```
#### 总结
之前总是同步到github 的时候总是报如下错误
```
Could not create directory '/c/Windows/system32/config/systemprofile/.ssh'.
```
如果你也遇到了同样的错误，那么我可以明确的告诉你。是你的系统环境变量冲突啦。s删除第一种方案的`HOME`变量和`_netrc`文件然后再去操作第二种方案！
下面是`stackoverflow`网友提供的思路，再次感谢；

When using a CYGWIN version of SSH you need to create an environment variable called HOME. If you create HOME as a System variable and set it to %USERPROFILE%, and cmd/bash gets launched as system (elevated), your %HOME% path will be C:\Windows\System32. 
An easy fix is to hardcode your userprofile path C:\Users\username to the HOME system variable, however if you have multiple users you will need to create environment variables accordingly. 
I was not implicitly launching cmd as SYSTEM however I was having this problem and not sure why. Safest option would be to only have a user environment variable called %USERPROFILE% and to not use an elevated command prompt.
If you're having this issue then run ECHO %HOME% and you'll see what the variable is being read as (or if it exists).



