---
title: 选择Hugo还是Hexo？
date: 2024-07-19 22:27:18
tags:
  - Blog
categories: Blog
---

# 全世界知名的两个静态网站生成器
## [Hexo](https://hexo.io/)：使用Node.js，~~这意味着你要忍受着`node_modules`无底洞~~
> 1. Node.js 所带来的超快生成速度。 上百个页面在几秒内完成渲染。
> 2. 强大的 API 带来无限的可能。 支持数种模板引擎（EJS，Pug，Nunjucks等）。 可以与现有的NPM包 (Babel, PostCSS, Less/Sass 等) 轻松地集成。
## [Hugo](https://gohugo.io)：使用Go语言，单文件，~~无需忍受`node_modules`无底洞~~
> The world’s fastest framework for building websites\
> 翻译：Hugo是世界上最快的构建网页框架
# 如何选择？
### 相同点：
- 都是使用命令行
- 均支持Markdown语法
- 都可以通过GitHub Pages或其他服务部署
- 支持元数据
### 不同点：
#### 两者间的FrontMatter的格式定义不同
- Hexo：
	1. 安装主题，插件等，需要通过`npm`安装
	2. 配置文件使用YAML
	3. 在生成较少文章时，是高效的、
	4. 提供了一系列主题和插件，在设计与功能上提供灵活
- Hugo：
	1. 主题目录与站点目录有一样的结构
	2. 安装主题使用`git submodule`，这在持续集成部署时也会方便很多
	3. 配置文件使用TOML
	4. 当在构建大型网站时，Hugo更胜一筹
	5. 拥有强大的模板系统，能更好地控制布局与结构，适于更复杂的自定义选项用户\
~~实在找不出来了，可以看看参考资料（本文也是基于以下两篇）~~
# 参考资料：
https://io-oi.me/tech/hugo-vs-hexo/
https://www.stackshare.io/stackups/hexo-vs-hugo