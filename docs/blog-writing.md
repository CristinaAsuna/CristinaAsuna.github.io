# 发布博客文章

博客主页为 <https://cristinaasuna.github.io/blog/>。每一篇文章都是 `_posts` 目录中的一个 Markdown 文件；推送到 GitHub 后，GitHub Pages 会自动发布。

## 新建文章

1. 在 `_posts` 下新建文件，文件名必须采用 `YYYY-MM-DD-slug.md` 格式。例如：`2026-08-24-my-first-post.md`。
2. 将下面的内容复制进去，填写标题、日期和正文。
3. 提交并推送到 GitHub，稍等片刻后文章会出现在博客列表中。

```markdown
---
title: "文章标题"
date: 2026-08-24
categories: [notes]
tags: [jekyll, blog]
excerpt: "一两句话概括本文内容。"
---

这里开始写正文。支持标准 Markdown：

## 二级标题

- 列表
- **加粗文字**

![图片说明](/images/blog/example.png)
```

## 图片与链接

- 将图片放到 `images/blog/`，正文用 `/images/blog/文件名` 引用。
- 站内链接建议使用以 `/` 开头的路径，例如 `[博客首页](/blog/)`。
- 文件名中的日期决定文章的发布日期；同一天可用不同的英文 slug 区分文章。
