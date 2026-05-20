# Xingxi's Space

一个使用 Hexo 与 Fluid 主题搭建的学术博客型个人网站，用于整理公共治理、政治学、城市研究与学术写作相关的笔记、项目和随笔。

## 本地安装

```powershell
npm install
```

## 本地预览

```powershell
npm run server
```

默认访问地址为 `http://localhost:4000/`。

## 生成静态文件

```powershell
npm run clean
npm run build
```

生成结果会输出到 `public/`，该目录已写入 `.gitignore`，不要提交到源码仓库。

## 新建文章

```powershell
npx hexo new "文章标题"
```

文章位于 `source/_posts/`。在文章 front matter 中可以设置分类与标签，例如：

```yaml
categories:
  - 随笔
tags:
  - 学术博客
  - 写作
```

## 在线写作后台

部署后可以访问：

```text
https://lapingris.github.io/fangchenkang.github.io/admin/
```

后台支持在线填写标题、分类、标签和 Markdown 正文，预览后发布到 GitHub。发布成功后会在仓库里创建或更新 `source/_posts/*.md` 文件，并触发 GitHub Actions 自动重新部署博客。

第一次使用前需要准备一个 GitHub fine-grained personal access token：

1. 打开 GitHub `Settings -> Developer settings -> Personal access tokens -> Fine-grained tokens`。
2. 选择当前博客仓库 `LapinGris/fangchenkang.github.io`。
3. Repository permissions 里把 `Contents` 设为 `Read and write`。
4. 生成 token 后，在 `/admin/` 页面的“仓库设置”里填入并保存。

token 只保存在当前浏览器的 `localStorage` 中，不会写入仓库。不要在公共电脑上保存 token。

## 页面结构

- 首页：`/`
- 归档：`/archives/`
- 分类：`/categories/`
- 标签：`/tags/`
- 研究项目：`/projects/`
- 论文写作：`/publications/`
- 关于：`/about/`

## GitHub Pages 部署

当前仓库发布在 `LapinGris` 账号下，仓库名为 `fangchenkang.github.io`，因此 GitHub Pages 地址是 `https://lapingris.github.io/fangchenkang.github.io/`。本项目提供 GitHub Actions 工作流，通过 Actions 构建 Hexo 并发布 `public/` 到 GitHub Pages。

启用方式：

1. 将源码推送到 GitHub 仓库。
2. 在仓库 `Settings -> Pages` 中，将 `Build and deployment` 的 `Source` 设为 `GitHub Actions`。
3. 推送到 `main` 分支后，`.github/workflows/pages.yml` 会执行构建与发布。

当前是 GitHub Pages 项目站点，发布路径是 `/fangchenkang.github.io/`，因此 Actions 构建时会额外读取 `_config.github.yml`。

## Vercel 部署

也可以使用 Vercel：

- Import Project：导入 `https://github.com/LapinGris/fangchenkang.github.io`
- Install Command：`npm install`
- Build Command：`npx hexo generate`
- Output Directory：`public`

Vercel 部署一般使用根路径 `/`。

## 常用维护命令

```powershell
npm install
npm run server
npm run clean
npm run build
```
