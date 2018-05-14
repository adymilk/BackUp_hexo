---
title: 在Ubuntu系统中安装hexo以及相关配置(记录贴)
date: 2017-03-29 00:37:04
tags: hexo
categories: Linux
---
### hexo 简介
A fast, simple & powerful blog framework
![hexo](http://oe3vwrk94.bkt.clouddn.com/hexo.png)
利用hexo可以快速的帮你搭建一个网站，通过把网站编译过的代码部署到个github page 和coding page免费提供的空间服务器上面。我们的网站就可以实现真正的免费上线了！而且还支持自定义域名和Markdown写作。通过免费搭建这样一个网站，可以记录个人的学习过程亦或展示一些你认为比较好的作品和大家一起学习分享！
<!-- more -->

如何去github 和coding注册账户，这里就不多说了（不会的话，擅用搜索引擎）

#### 1、安装git

git是地球上最先进的版本管理控制系统，与时俱进的程序员、黑客、作家都在用它。

```
$ sudo apt-get install git-core
```
#### 2、安装npm (node package manager)

英文全称是node包的管理工具。

```
$ sudo apt-get install npm
```

#### 3、安装nodejs-legacy

```
$ sudo apt-get install nodejs-legacy
```

#### 4、安装hexo

输入下面命令，开始安装hexo

```
npm install hexo-cli -g

npm install hexo -g
```

### 启动服务

安装Hexo安成后，使用如下命令快速新建一个博客系统，然后运行它：

```
hexo init blog
cd blog
hexo server

```
此时在浏览器输入**localhost:4000**看看是否可以打开网站


### 部署到hexo 和coding

配置站点`_config.yml`文件,我的配置如下

```
# Hexo Configuration
## Docs: https://hexo.io/docs/configuration.html
## Source: https://github.com/hexojs/hexo/

# Site
title: 三步枫同学的博客
subtitle:
description:
author: 三步枫
language: 
timezone:

# URL
## If your site is put in a subdirectory, set url as 'http://yoursite.com/child' and root as '/child/'
url: http://adymilk.cn/
root: /
permalink: :year/:month/:day/:title/
permalink_defaults:

# Directory
source_dir: source
public_dir: public
tag_dir: tags
archive_dir: archives
category_dir: categories
code_dir: downloads/code
i18n_dir: :lang
skip_render:

# Writing
new_post_name: :title.md # File name of new posts
default_layout: post
titlecase: false # Transform title into titlecase
external_link: true # Open external links in new tab
filename_case: 0
render_drafts: false
post_asset_folder: false
relative_link: false
future: true
highlight:
  enable: true
  line_number: true
  auto_detect: false
  tab_replace:

# Category & Tag
default_category: uncategorized
category_map:
tag_map:

# Date / Time format
## Hexo uses Moment.js to parse and display date
## You can customize the date format as defined in
## http://momentjs.com/docs/#/displaying/format/
date_format: YYYY-MM-DD
time_format: HH:mm:ss

# Pagination
## Set per_page to 0 to disable pagination
per_page: 7
pagination_dir: page

# Extensions
## Plugins: https://hexo.io/plugins/
## Themes: https://hexo.io/themes/
theme: landscape

# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: git
  repo:
    github: git@github.com:adymilk/adymilk.github.io.git,master #github的地址
    coding: git@git.coding.net:xfhelp/xfhelp.git,master #coding的地址
  branch: master

```

### 配置ssh key

1、打开终端，输入命令
```
ls -al ~/.ssh
```
检查是否显示有id_rsa.pub或者id_dsa.pub存在，如果存在请直接跳至第4步。

键入
```
ssh-keygen -t rsa -C"your_email@example.com"
```
注意将这里的邮箱地址替换成你自己的邮箱地址。之后一直回车！这时候你可以看到id_rsa和id_rsa.pub文件已经生成。并且生成的路径也已显示。

用记事本之类的软件打开id_rsa.pub文件，并且复制全部内容到github和coding对应的ssh key填入。


**最后一条命令**
编译并部署代码到github和coding上面
``
hexo g -d
```

### 大功告成！




