---
title: '在Ubuntu下解决 adb devices:xx no permission '
date: 2017-06-26 18:11:44
tags:
- ubuntu
- adb
categories: 代码笔记
---

原因分析：因为ubuntu这样的系统都是默认以非root身份在运行的，要使用usb调试，需要sudo支持。
so:这样来解决问题～

### One step
```
sudo adb kill-server
```

### Two step
```
sudo adb devices
```
**这时候回向手机请求调试申请，请给予手机同意adb调试**

问题解决。

### adb 安装apk
```
sudo adb install xxxx.apk
```

