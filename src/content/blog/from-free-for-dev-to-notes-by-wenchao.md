---
title: '从 free-for-dev 到 Notes by Wenchao：一次 AI Agent 协作建站记录'
description: '记录一次从免费资源清单出发，用 AI Agent 完成个人博客选型、搭建、部署和自动化维护的过程。'
pubDate: '2026-04-30'
---

这篇文章记录本站的诞生过程。

起点很简单：我把 [free-for-dev](https://free-for.dev/) 丢给 AI Agent，说想搭一个自己的博客网站，让它参考一下。

它一开始理解错了。

它以为我要参考 free-for-dev 的网站形态，做一个类似“资源目录站”的东西。但我的意思不是这个。我真正想要的是：参考 free-for-dev 里列出来的免费开发者资源，看看哪些服务可以被用来搭建和维护一个低成本、低维护的个人博客。

这个纠偏之后，事情才开始变得清楚。

## 不是模仿网站，而是借用资源

free-for-dev 的价值，不在于它的网站样式，而在于它长期维护了一张免费服务地图。

对一个个人博客来说，真正需要的不是复杂系统，而是几个可靠的基础能力：

- 代码和文章放在哪里；
- 静态页面在哪里构建；
- 站点托管在哪里；
- 搜索、评论、统计要不要接；
- 以后如何自动部署；
- 这些东西能不能尽量免费、稳定、少折腾。

最后选出来的是一套很朴素的组合：

- GitHub：管理源码和 Markdown 内容；
- Astro：生成静态博客；
- Cloudflare Pages：托管和部署；
- Pagefind：静态站内搜索；
- RSS / sitemap：基础发布能力；
- Utterances：如果需要评论，可以用 GitHub Issues 承接；
- Cloudflare Web Analytics：如果需要统计，可以轻量接入。

这里的判断是：个人博客初期不需要数据库，不需要复杂 CMS，也不需要过度设计。

先让网站跑起来。

## 从 wc-blog 到 notesbywenchao

最开始给出的名字还很随意：

- 博客名：`wc notes`
- 仓库名：`wc-blog`

AI Agent 直接在本地创建了 Astro blog 项目，装依赖，改配置，删掉默认示例文章，补上首页、About、Resources、Search 页面，再接上 RSS、sitemap 和 Pagefind。

早期项目路径是：

```text
/Users/huangwenchao/wc-blog
```

后来这个项目继续演进，名字也变得更正式：

```text
Notes by Wenchao
```

本地路径迁移到：

```text
/Users/huangwenchao/workspace/notesbywenchao
```

GitHub 仓库也从：

```text
suprewen/wc-blog
```

变成：

```text
suprewen/notesbywenchao
```

最终站点地址是：

```text
https://notesbywenchao.pages.dev
```

中间没有什么神奇技术。更多是一些琐碎但必要的执行：初始化项目、改站点名、清理模板内容、跑 build、建 GitHub 仓库、推送代码、部署到 Cloudflare Pages。

这正是 AI Agent 很适合做的事。

它不一定比人更懂“我要写什么”，但它很适合把一串明确的工程步骤连续执行完。

## 自动部署比手动部署重要

网站能上线只是第一步。

如果每次写文章都要手动构建、手动上传、手动检查，那么博客很快会变成负担。

所以后面又给这个仓库配置了 GitHub Actions。

现在流程是：

1. 写文章到 `src/content/blog/`；
2. 本地执行 `npm run build`；
3. commit；
4. push 到 `main`；
5. GitHub Actions 自动构建；
6. 自动部署到 Cloudflare Pages。

Cloudflare 相关的 credential 放在 GitHub Secrets 里：

- `CLOUDFLARE_ACCOUNT_ID`
- `CLOUDFLARE_API_TOKEN`

token 不进入仓库，也不写进笔记。

这一步完成后，博客就从“一个已经上线的网站”变成了“一个可以持续发布的系统”。

## Obsidian 是工作台，博客是展厅

搭完博客之后，真正重要的问题反而出现了：以后怎么维护？

我不想把博客变成另一个杂乱笔记库。

现在的分工是：

- Obsidian learn vault 是工作台；
- Notes by Wenchao 是展厅。

Obsidian 里可以放：

- 原始资料；
- 阅读笔记；
- 概念理解；
- 临时想法；
- 研究过程；
- 半成品结论。

博客里只放：

- 已经想清楚的文章；
- 可公开的技术笔记；
- 资源整理；
- 方法论总结；
- 项目复盘；
- 未来还能引用的内容。

这也是我后来对这个站点的定位：它不是日记，也不是资料仓库，而是一个公开知识输出站。

## 这次协作里，人的作用是什么

这次流程里，AI Agent 做了很多执行工作。

但最关键的转折，仍然来自人的纠偏。

一开始它误解了 free-for-dev 的用法。如果我不指出“我是让你参考里面的免费资源，不是模仿它的网站思路”，后面很可能就会走偏。

所以这次经验不是“AI Agent 全自动搭好了博客”。

更准确地说，是：

> 人给目标和判断，Agent 做搜索、选型、执行和验证。

人的作用是决定方向：

- 我要的不是资源目录站；
- 我要的是自己的个人博客；
- 我关心免费资源，但不想堆复杂系统；
- 我希望能长期维护，而不是只上线一次；
- 我希望 Obsidian 和博客分工明确。

Agent 的作用是把这些判断落到文件、命令、仓库和部署上。

## 最终形成的发布流水线

现在这套流程可以概括为：

```text
资料 / 链接 / 讨论
        ↓
Obsidian learn vault
        ↓
理解、拆解、沉淀
        ↓
筛选稳定主题
        ↓
整理成博客文章
        ↓
写入 Notes by Wenchao
        ↓
npm run build
        ↓
git commit + push
        ↓
GitHub Actions
        ↓
Cloudflare Pages
        ↓
notesbywenchao.pages.dev
```

这个流程比“搭一个博客”本身更重要。

博客上线只是结果。真正有价值的是：我现在有了一条从学习、理解、沉淀到公开发布的路径。

## 小结

这次从 free-for-dev 到 Notes by Wenchao 的过程，让我更确定几件事：

1. 个人博客应该先保持简单；
2. 免费开发者服务已经足够支撑一个长期博客；
3. AI Agent 很适合做连续工程执行；
4. 人仍然要负责判断、纠偏和取舍；
5. 博客不应替代知识库，而应发布知识库中已经稳定的东西；
6. 自动部署是降低维护成本的关键。

所以，这个网站不是从一个完整规划开始的。

它是从一个链接、一句纠正、一次选型和一串自动化执行里长出来的。

这可能也是我希望以后继续使用 AI Agent 的方式：不是让它替我思考一切，而是让它把已经想清楚的方向，尽快变成可以运行、可以验证、可以维护的东西。
