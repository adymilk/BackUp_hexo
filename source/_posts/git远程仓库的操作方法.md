---
title: git远程仓库的操作方法
date: 2017-08-08 11:43:51
tags:
- git
- github
categories: 代码笔记
---

### Quick setup — if you’ve done this kind of thing before

> or `HTTPS`  `SSH` git@github.com:adymilk/materializecss-admin-management.git

We recommend every repository include a README, LICENSE, and .gitignore.


### or create a new repository on the command line
```
echo "# materializecss-admin-management" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:adymilk/materializecss-admin-management.git
git push -u origin master
```

### or push an existing repository from the command line
```
git remote add origin git@github.com:adymilk/materializecss-admin-management.git
git push -u origin master
```

### or import code from another repository

> You can initialize this repository with code from a Subversion, Mercurial, or TFS project.


### 如果远程仓库与本地仓库存在冲突
```
//先把远程仓库代码拉下来
git pull git@https://github.com/adymilk/project

//在重新push
git push origin master
```

### 强制合并
```
git push origin master --force
```

### 代码回滚
```
git reset --hard 【版本号】
```

