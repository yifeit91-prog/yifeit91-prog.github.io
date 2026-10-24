---
layout: post
title: 一篇文章是怎么变成网页的
date: 2026-10-21
excerpt: 从 _posts 里的一个 Markdown 文件，到浏览器里可以访问的页面。
tags:
  - Jekyll
  - 学习
---

在这个博客里写文章，只需要在 `_posts` 目录新建一个 Markdown 文件，文件名按 `YYYY-MM-DD-title.md` 命名。

## 文件开头的 Front Matter

每个文件开头有一段被 `---` 包住的内容：

```yaml
---
layout: post
title: 文章标题
date: 2026-10-21
excerpt: 一句话摘要
tags:
  - 学习
---
```

这段叫 Front Matter，Jekyll 会读取它：`layout: post` 决定用哪个模板，`title` 和 `date` 显示在页面上，`tags` 出现在标题下方。

## 发布时发生了什么

1. 我把文件提交并推送到 GitHub。
2. GitHub Actions 启动，用 Jekyll 把 Markdown 编译成 HTML。
3. 生成好的文件被发布到 GitHub Pages。
4. 浏览器访问到的就是最终的页面。

本地不需要安装 Ruby 或 Jekyll，构建全部发生在 Actions 里。

## 链接长什么样

`_config.yml` 里的 `permalink: /posts/:title/` 决定了文章地址的格式，所以一篇文章的 URL 大致是：

```text
https://yifeit91-prog.github.io/posts/from-markdown-to-page/
```

记住这个流程，写新文章就只是复制、改名、写正文、推送。
