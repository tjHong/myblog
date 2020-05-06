---
title: 基于Hexo + GitHub Pages的个人博客搭建
date: 2018-06-07 14:29:12
type: "tags"
tags: 
  - blog
---
![Alt text](/images/hexo_github.jpg)
# 摘要
这是一篇关于如何利用 Hexo 框架快速搭建个人博客，并将其部署在 GitHub Pages 的文章。

# 前提
Hexo 的本地安装需要 Node.js 环境，未来在 GitHub Pages 的部署还需要利用 git。所以本地对 Node.js 及 git 的支持是必须的。

# 一、 安装 Hexo
__我们先来安装 hexo-cli__

    npm install hexo-cli -g
命令将会在全局安装 hexo (本文 hexo 版本为 3.7.1 ，hexo-cli 版本 1.1.0)
hexo 在 github 的地址：[https://github.com/hexojs/hexo](https://github.com/hexojs/hexo)

__在本地创建 myblog 文件夹，并初始化 hexo__

    hexo init myblog
    cd myblog
    npm install
__Hexo 几个常用的命令：__

    hexo generate (hexo g)     生成静态文件，会在当前目录下生成一个新的叫做public的文件夹
    hexo server (hexo s)       启动本地web服务，用于博客的预览
    hexo deploy (hexo d)       部署博客到远端服务器
    hexo new "postName"        新建文章
    hexo new page "pageName"   新建页面

# 二、GitHub Pages 设置
GitHub Pages 可以被认为是用户编写的、托管在 github 上的静态网页。GitHub Pages 本用于介绍托管在GitHub的项目，不过，由于他的空间免费稳定，用来做搭建一个博客再好不过了。

__创建仓库：__

![Alt text](/images/github01.png)这里仓库的命名必须是 username/username.github.io，这是特殊的命名约定。

# 三、部署到 GitHub
开始这一步之前，需要确保你的电脑与你的 github 账户之间已经配置了 SSH-Key

__安装 hexo-deployer-git 包，执行以下命令__

    npm install hexo-deployer-git --save

__生成静态文件并部署到 gitHub__

    hexo d -g