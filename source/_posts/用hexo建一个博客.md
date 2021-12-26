---
title: 用hexo建一个博客
date: 2021-12-23 22:09:28
cover: https://kkksx.github.io/2021/12/23/用hexo建一个博客/cover.png
comments: true
aplayer: true
tags: hexo
---

## 前言

今天自学了一下用hexo在github上面搭建博客，本文作为博客的第一篇文章，记录一下一些状况

操作系统为win10

## 做一个博客

在要创建本地博客目录的地方打开git bash，输入hexo init <仓库名>来创建一个仓库，仓库名应该是用"用户名.github.io"，这条指令事实上就是将github上的hexo_starter clone到本地，会比较慢，成功会显示

```git
INFO  Start blogging with Hexo!
```

之后cd进入博客文件夹，输入npm install和npm install hexo-deployer-git下载对应的依赖

博文存储在./source/_posts里面

用以下指令可以生成一个静态页面，并将其部署到github上面

```
hexo clean  // 大概是每次都要用，用于清空缓存，防止错误
hexo generator (g)  // 生成静态页面，可以看到多了一个public文件夹，里面存储之后会放到github上面去的页面
hexo deploy (d)  // 将静态页面部署到github上面去，该步骤需要网速
```

在hexo deploy操作前，需要修改_config.yml文件最后的部分，来告诉deploy应该部署到哪里去

```
deploy:
  type: git
  repo: https://github.com/kkksx/kkksx.github.io
  branch: main  // github将默认分支从master改成了main，这里应该是main
  message: update hexo static page  // 可选
```

hexo deploy操作也是相当的慢，而且中途可能会要求输入账号密码，这里的密码要用在github setting里面生成的token，因为目前github不支持账密验证







