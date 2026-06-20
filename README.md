# XIE YIFAN

基于 Astro 构建的个人博客站点，深色主题，简洁优雅。

## 功能

- 博客文章 — 基于 Content Collections 管理，Markdown 编写
- 关于页面 — 个人介绍、荣誉展示、证书瀑布流（点击放大查看）
- 项目展示 — 展示 GitHub 开源项目，点击跳转仓库
- 深色主题 — 玻璃拟态导航栏、渐变光晕背景
- 响应式 — 适配桌面端与移动端
- 静态生成 — 零 JavaScript，加载极快

## 项目结构

```
/
├── public/
│   ├── certificates/       # 证书图片
│   └── favicon.webp        # 站点图标
├── src/
│   ├── content/
│   │   └── blog/           # 博客文章（Markdown）
│   ├── layouts/
│   │   └── Layout.astro    # 全局布局
│   └── pages/
│       ├── index.astro     # 首页
│       ├── about.astro     # 关于页面
│       ├── projects.astro  # 项目展示页
│       ├── posts.astro     # 文章列表页
│       └── posts/
│           └── [slug].astro # 文章详情页
├── content.config.ts       # Content Collections 配置
├── astro.config.mjs        # Astro 配置
└── package.json
```

## 本地开发

```bash
# 安装依赖
npm install

# 启动开发服务器
npm run dev

# 构建生产版本
npm run build

# 本地预览构建结果
npm run preview
```

## 部署

项目为纯静态站点，构建产物在 dist/ 目录，支持部署到任意静态托管平台。

### Cloudflare Pages

1. 将代码推送到 GitHub 仓库
2. 登录 Cloudflare Dashboard，进入 Pages
3. 连接 GitHub 仓库
4. 设置构建命令为 `npm run build`，输出目录为 `dist`
5. 绑定自定义域名

### Vercel / Netlify

连接 GitHub 仓库即可自动部署，零配置。

## 添加文章

在 `src/content/blog/` 目录下新建 Markdown 文件，文件名即为文章 URL slug。

文件头部需要包含 frontmatter：

```yaml
---
title: 文章标题
description: 文章描述
date: 2026-05-08
tags:
    - 标签1
    - 标签2
---
```

## 添加项目

编辑 `src/pages/projects.astro`，在 `projects` 数组中添加新项目：

```js
const projects = [
    {
        name: '项目名称',
        description: '项目描述',
        url: 'https://github.com/xxx/xxx',
        tags: ['技术1', '技术2'],
    },
];
```

## 添加证书

编辑 `src/pages/about.astro`，将证书图片放入 `public/certificates/` 目录，然后在 `certificates` 数组中添加：

```js
const certificates = [
    {
        image: '/certificates/图片名.jpeg',
        title: '证书名称（可选）',
    },
];
```

## 添加荣誉

编辑 `src/pages/about.astro`，在 `awards` 数组中添加：

```js
const awards = [
    {
        title: '荣誉名称',
        tag: '名次或等级',
    },
];
```

## 技术栈

- Astro 6 — 静态站点生成器
- Markdown + Content Collections — 内容管理
- 纯 CSS — 无框架依赖，手写样式
