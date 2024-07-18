---
title: 使用Hugo搭建Blog
date: 2024-07-18 12:00:59
tags: Blog
categories: Blog
---
# Hugo介绍
> Hugo是世界上最快的构建网页的框架\
——[ Hugo官网 ](https://gohugo.io/)
# 安装Hugo
Arch Linux：
```
sudo pacman -S hugo
```
其余发行版请自行使用包管理器搜索并安装
# 开始使用
首先创建一个空白网页
{% note warning %}
Warning:请不要使用Cloudflare Pages部署
{% endnote %}
```
hugo new site <Site_name>
```

