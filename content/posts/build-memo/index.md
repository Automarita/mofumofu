---
title: 站点建设备忘
subtitle: null
date: 2021-12-19T15:25:59.471Z
summary: Wowchemy 建站
draft: false
featured: false
authors:
  - admin
lastmod: 2021-12-19T21:00:00.000Z
tags:
  - Wowchemy
  - Netlify
categories:
  - memo
projects: []
---
## Intro

将相对简单的结构样式配置和图文资源编译成可供浏览器展现的网页资源（HTML/CSS/JavaScript）是现代个人网站建设的一般模式。

借助 Hugo 静态资源渲染引擎，Wowchemy 提供了相对低代码的模版，和在 Netlify 托管的脚本。我们在 Netlify 上注册了一个静态网站项目，在 GitHub 上 fork 了一份来自 Wowchemy 的模版，同时授权项目监听 GitHub 仓库的代码提交，当自建仓库对应的代码分支发生新的提交事件时，Netlify 项目立即触发一次编译和部署，如果没有出错，更新的内容或配置将立即在 Netlify 托管的页面上生效。

{{< figure src="wowchemy-netlify.png" title="你需要理解简单的配置如何转化成网页资源，以及，Netlify 「部署」时发生了什么" >}}

## Debug

仅仅使用模版不能完全切合我们的使用需求，所以需要修改和调试从 Wowchemy fork 过来的模版代码。在 VSCode 中打开模版代码，列出主要的文件构成：
```
_____
  |__ assets
  |__ static
  |__ scripts
  |__ data
  |__ content
  |      |__ authors
  |      |__ home
  |      |__ post
  |      |__ publication
  |      |__ ...
  |
  |__ config
  |__ ... 
  |__ ... 
``` 

初次访问，主页面由顶部导航栏和垂直铺设的若干个 section 构成。我们不需要那么多 section，而且，还需要调整一下 section 的排列顺序。阅读官方文档可知，页面所有内容几乎集中在 `/content` 中，而主页面设计则在 `/content/home` 目录下。而目录中又有数个 markdown 文件，仔细观察可以确认这些 markdown 分别对应了主页的几个 section，打开发现这些文件其实不是纯粹的 markdown，头部被三短线包裹住的部分是 yaml 配置。比如在`about.md`，我们发现，每个配置项都有 # 开头的注释仔细说明，从注释中还可以读到，`active` 配置了此 section 是否显示，weight 配置了此 section 的相对位置。

接下来要调整的是个人简介，简介中的文字在哪里呢？ `about.md` 中的注释告诉了你如何编写配置，它指向了官方文档中的[一段文字](https://wowchemy.com/docs/get-started/#introduce-yourself)。在实现和查阅过程中，同时也逐渐理解了 Wowchemy 这份模版的一些特性。



## Features

* **Page builder** - Create *anything* with **[widgets](https://wowchemy.com/docs/page-builder/)** and **[elements](https://wowchemy.com/docs/content/writing-markdown-latex/)**
* **Edit any type of content** - Blog posts, publications, talks, slides, projects, and more!
* **Create content** in **[Markdown](https://wowchemy.com/docs/content/writing-markdown-latex/)**, **[Jupyter](https://wowchemy.com/docs/import/jupyter/)**, or **[RStudio](https://wowchemy.com/docs/install-locally/)**
* **Plugin System** - Fully customizable [**color** and **font themes**](https://wowchemy.com/docs/customization/)
* **Display Code and Math** - Code highlighting and [LaTeX math](https://en.wikibooks.org/wiki/LaTeX/Mathematics) supported
* **Integrations** - [Google Analytics](https://analytics.google.com), [Disqus commenting](https://disqus.com), Maps, Contact Forms, and more!
* **Beautiful Site** - Simple and refreshing one page design
* **Industry-Leading SEO** - Help get your website found on search engines and social media
* **Media Galleries** - Display your images and videos with captions in a customizable gallery
* **Mobile Friendly** - Look amazing on every screen with a mobile friendly version of your site
* **Multi-language** - 34+ language packs including English, 中文, and Português
* **Stand Out** - Bring your site to life with animation, parallax backgrounds, and scroll effects
* **One-Click Deployment** - No servers. No databases. Only files.

{{< figure src="https://www.kinggoya.com/wp-content/uploads/2014/09/train-summer-med1-1068x580.jpg" title="测试图片（侵删）" >}}

## License

**CC-BY-NC-SA**