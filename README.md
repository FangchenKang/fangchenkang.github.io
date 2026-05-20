# Fangchen's Space

这是 Fangchen Kang 的 Hexo + Fluid 学术博客项目，用于整理个人简介、研究项目、阅读笔记和普通博客文章。当前网站按 GitHub Pages 用户主页方式部署，线上地址为：

https://fangchenkang.github.io/

## 本地使用

安装依赖：

```bash
npm install
```

本地预览：

```bash
npx hexo server
```

生成静态文件：

```bash
npx hexo clean
npx hexo generate
```

生成后的文件会放在 `public/` 目录中。这个目录已经写入 `.gitignore`，不要手动提交。

## 写普通博客文章

普通文章放在 `source/_posts/` 目录。可以直接新建 Markdown 文件，例如：

```text
source/_posts/my-new-post.md
```

文章顶部建议使用这样的 Front Matter：

```markdown
---
title: 文章标题
date: 2026-05-20 20:00:00
categories:
  - 随笔
tags:
  - 学术博客
  - 写作
---

正文内容。
```

## 新增研究项目

研究项目入口页是：

```text
source/projects/index.md
```

每个项目详情页放在 `source/projects/` 下面的独立文件夹中，例如：

```text
source/projects/my-project/index.md
```

新增项目时，可以复制现有项目详情页，例如：

```text
source/projects/zongzhi/index.md
```

然后修改标题、导语和正文内容。详情页中已经预留目录结构：

- 项目概述
- 研究问题
- 数据与材料
- 方法与工具
- 阶段进展
- 后续计划
- 相关笔记

如果要让新项目出现在项目首页，需要在 `source/projects/index.md` 的卡片列表中复制一个 `<article class="library-card project-card">...</article>`，把标题、说明、标签和链接改成新项目路径。

## 新增阅读笔记

阅读入口页是：

```text
source/reading/index.md
```

每条阅读笔记放在 `source/reading/` 下面的独立文件夹中，例如：

```text
source/reading/my-reading-note/index.md
```

新增阅读笔记时，可以复制现有模板，例如：

```text
source/reading/xiangtu-china/index.md
```

阅读笔记中已经预留目录结构：

- 文献信息
- 阅读问题
- 章节目录
- 核心观点
- 关键概念
- 摘录与评论
- 延伸思考

如果要让新笔记出现在阅读首页，需要在 `source/reading/index.md` 的卡片列表中复制一个 `<article class="library-card reading-card">...</article>`，修改标题、作者、说明、标签和链接。

## 添加封面和项目图片

书籍或文献封面建议放在：

```text
source/img/covers/
```

项目图片建议放在：

```text
source/img/projects/
```

当前已经放了两个默认占位图：

```text
source/img/covers/default-book-cover.svg
source/img/projects/default-project.svg
```

以后替换封面时，把图片放到对应目录，然后在 `source/reading/index.md` 或 `source/projects/index.md` 中修改图片路径即可。例如：

```html
<img src="/img/covers/my-book-cover.jpg" alt="书名">
```

## 关于在线编辑

这个项目目前采用稳定的静态博客方案：用 Markdown 文件管理文章、项目和阅读笔记，用 GitHub 或 VS Code 管理图片与文本，再通过 GitHub Actions 或本地命令生成静态网页。

GitHub Pages 本身不提供数据库，也不能像公众号后台那样直接保存在线编辑内容。本仓库里不做假的在线编辑器。以后如果确实需要网页后台、上传图片和自动目录，可以再考虑接入 Decap CMS、TinaCMS，或者使用 GitHub 网页编辑流程。

## 提交与推送

修改内容后，先本地生成检查：

```bash
npm install
npx hexo clean
npx hexo generate
```

确认无误后提交并推送：

```bash
git add .
git commit -m "update content"
git pull --rebase origin main
git push origin main
```

当前远程仓库应为：

```text
https://github.com/FangchenKang/fangchenkang.github.io.git
```
