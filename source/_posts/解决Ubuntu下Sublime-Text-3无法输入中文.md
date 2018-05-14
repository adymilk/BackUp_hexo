---
title: 解决Ubuntu下Sublime Text 3无法输入中文
date: 2017-07-29 19:20:03
tags: Ubuntu
categories: Linux
---
### 故障产生原因
> Ubuntu(Debian) 系统下的无法输入中文(CJK 字符)输入法的问题！官方并没有给出Sublime-Text的修复。

### 解决办法
* github开源补丁
地址：https://github.com/lyfeyaj/sublime-text-imfix

#### 使用方法：

* 更新并升级系统为最新(较新的系统会解决很多可能出现的问题)

```
sudo apt-get update && sudo apt-get upgrade

```

* 克隆项目到本地 :

```
git clone https://github.com/lyfeyaj/sublime-text-imfix.git
```

* 运行脚本 :

```
cd sublime-text-imfix && ./sublime-imfix

```

* 完成! 重新启动后就可以在 Sublime Text 2/3 中 使用 Fcitx了! 注意: 皮肤可能需要自己选择 ^_^


<!-- more -->
