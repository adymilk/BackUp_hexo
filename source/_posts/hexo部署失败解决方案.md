---
title: hexo部署失败解决方案
date: 2016-09-23 15:48:20
categories: web
---
![](http://www.bkjia.com/uploads/allimg/150420/16320J252-4.png)
<dt>hexo部署失败 ERROR Deployer not found: git,你是不是也遇到了这个问题呢？这篇文章可以帮助你解决</dt>
<!-- more -->

·hexo已升级3.0
命令 hexo g 没有办法成功deploy，

文档说hexo3.0后需要在 _config.yml 中设置 deploy中的type为git（过去是github），

然后，记得一定要在 blog 目录里 执行 npm install hexo-deployer-git --save ，

因为，你一定记得当初...
```
 npm install hexo-cli -g
    hexo init blog
    cd blog
    npm install
    hexo server
```
否则，你就老老实实的重头开始一边咯
ssh-keygen -t rsa -b 4096 -C "your email"
记得把 SSH keys 添加到github上  Personal settings ->SSH keys->Add SSH keys
先测试一下
```
ssh -T git@github.com
Hi Xuser! You've successfully authenticated ......
hexo d
INFO  Deploying: git
INFO  Clearing .deploy folder...
INFO  Copying files from public folder...
位于分支 master
```

