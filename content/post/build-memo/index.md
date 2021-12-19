---
title: 站点建设备忘
subtitle: null
date: 2021-12-19T15:25:59.471Z
summary: Wowchemy 建站
draft: false
featured: false
authors: admin
lastmod: 2021-12-19T21:00:00Z
tags:
  - Wowchemy
  - Netlify
categories:
  - memo
projects: []
---

## 总括

借助 Wowchemy 提供的模版和 Hugo 静态网站渲染引擎，将相对简单的样式配置和图文资源编译成可供浏览器展现的网页资源（指 HTML/CSS/JavaScript），这就是现代个人网站建设的一般模式。由于 Wowchemy 同时提供在 Netlify 托管渲染的执行脚本，我们在 Netlify 上注册了本项目，Wowchemy 提供的模板和我们自己的样式配置、图文资源同步更新在 GitHub 的自建仓库中，为提高效率，同时授权 Netlify 项目监听自建仓库的代码提交，当自建仓库对应的代码分支发生新的提交事件时，Netlify 项目立即触发一次编译和部署，如果没有差错产生，更新的内容或配置将立即在 Netlify 托管的页面上生效。

{{< figure src="/static/media/wowchemy-netlify.svg" title="你需要理解简单的配置如何转化成网页资源，以及，Netlify 「部署」时发生了什么" >}}

## Features

- **Page builder** - Create *anything* with [**widgets**](https://wowchemy.com/docs/page-builder/) and [**elements**](https://wowchemy.com/docs/content/writing-markdown-latex/)
- **Edit any type of content** - Blog posts, publications, talks, slides, projects, and more!
- **Create content** in [**Markdown**](https://wowchemy.com/docs/content/writing-markdown-latex/), [**Jupyter**](https://wowchemy.com/docs/import/jupyter/), or [**RStudio**](https://wowchemy.com/docs/install-locally/)
- **Plugin System** - Fully customizable [**color** and **font themes**](https://wowchemy.com/docs/customization/)
- **Display Code and Math** - Code highlighting and [LaTeX math](https://en.wikibooks.org/wiki/LaTeX/Mathematics) supported
- **Integrations** - [Google Analytics](https://analytics.google.com), [Disqus commenting](https://disqus.com), Maps, Contact Forms, and more!
- **Beautiful Site** - Simple and refreshing one page design
- **Industry-Leading SEO** - Help get your website found on search engines and social media
- **Media Galleries** - Display your images and videos with captions in a customizable gallery
- **Mobile Friendly** - Look amazing on every screen with a mobile friendly version of your site
- **Multi-language** - 34+ language packs including English, 中文, and Português
- **Stand Out** - Bring your site to life with animation, parallax backgrounds, and scroll effects
- **One-Click Deployment** - No servers. No databases. Only files.

{{< figure src="https://www.kinggoya.com/wp-content/uploads/2014/09/train-summer-med1-1068x580.jpg" title="测试图片（侵删）" >}}
## License

**CC-BY-NC-SA**