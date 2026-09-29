---
title: hexo从GitHub上克隆到本地
date: 2024-07-03 14:51:48
tags:
---

hexo从GitHub上克隆到本地-恢复使用操作

1. [hexo从GitHub上克隆到本地-恢复使用操作](https://evansleesin.github.io/2024/07/02/hexo从GitHub上克隆到本地-恢复使用操作/#hexo从GitHub上克隆到本地-恢复使用操作)

## [hexo从GitHub上克隆到本地-恢复使用操作](https://www.cnblogs.com/eidolonw/p/13070099.html)

**一、配置环境**

**1.安装git**（点击进入[Git官网](https://git-scm.com/downloads)，如果嫌下载慢自行百度解决~） 

**2.Git与远程库进行\**SSH授权\****(点击查看教程[Git的安装-与远程仓库GitHub配置](https://www.cnblogs.com/wy0526/p/13068373.html))**
**

**2.安装node.js** （点击进入[nodejs官网](https://nodejs.org/zh-cn/)直接下载）

**二.\**配置本地博客\****

**1.安装hexo**

```
npm install -g hexo-cli
```

安装好后不需要初始化（hexo init） 

**2.克隆GitHub上保存的hexo网站原文件**

```
git clone git@github.com:Rainbow0526/Rainbow0526.github.io.git
```

**3.生成缺少的网站文件**

进入克隆的目录，执行：

```
npm install
npm install hexo-deployer-git --save
```

因为上传GitHub时有.gitignore文件，所以上传到github上默认是忽略掉 node_modules等文件夹，即仓库的hexo分支并没有存储这些文件，所以需要install生成。

**三.生成、部署（推荐）**

```
hexo g
hexo d
```

刚恢复本地hexo最好生成部署一下，接下来就像以前一样了。

 参考资料1：https://www.zhihu.com/question/21193762/answer/489124966

参考资料2：https://www.jianshu.com/p/0b1fccce74e0
