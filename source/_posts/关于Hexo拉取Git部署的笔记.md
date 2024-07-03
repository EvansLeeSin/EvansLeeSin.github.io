---
title: 关于Hexo拉取Git部署的笔记
date: 2024-07-03 17:00:14
tags:hexo
---



Hexo

#### 关于首次将Hexo部署到本地，并提交至GitHub

实现的内容是将Hexo的静态页面提交至GitHub的main分支下，源代码部分则是resource分支
若是下次在一台新电脑上进行部署，就只需要将源代码拉下，并进行本地构建，再将静态页面发布至main分支

下面描述操作流程

##### 安装hexo

```
npm install -g hexo
```

##### 克隆GitHub上的项目源代码(resource分支)

```
git clone git@github.com:EvansLeeSin/EvansLeeSin.github.io.git
```

##### 生成缺少的网站文件

进入克隆的目录执行:

```
npm install
npm install hexo-deployer-git --save
```

因为上传GitHub时有.gitignore文件，所以上传到github上默认是忽略掉 node_modules等文件夹，即仓库的hexo分支并没有存储这些文件，所以需要install生成。

##### 生成、部署

可以先测试下本地启动展示是否正常

```
hexo s
```

生成静态网页，并部署到GitHub的main分支

```
hexo g
hexo d
```

