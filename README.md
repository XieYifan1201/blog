# 1FanX 的博客

基于 [Astro](https://astro.build) 构建的个人博客站点，深色主题，简洁优雅。

## 功能

- � 博客文章 — 基于 Content Collections 管理，Markdown 编写
- � 关于页面 — 个人介绍、荣誉展示、证书瀑布流（点击放大查看）
- 🌙 深色主题 — 玻璃拟态导航栏、渐变光晕背景
- 📱 响应式 — 适配桌面端与移动端
- ⚡ 静态生成 — 零 JavaScript，加载极快

## 项目结构

```
/
├── public/
│   ├── certificates/       # 证书图片
│   └── favicon.jpeg        # 站点图标
├── src/
│   ├── content/
│   │   └── blog/           # 博客文章（Markdown）
│   ├── layouts/
│   │   └── Layout.astro    # 全局布局
│   └── pages/
│       ├── index.astro     # 首页
│       ├── about.astro     # 关于页
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

项目为纯静态站点，构建产物在 `dist/` 目录，支持部署到任意静态托管平台：

- **Cloudflare Pages** — 连接 GitHub 仓库，构建命令 `npm run build`，输出目录 `dist`
- **Vercel / Netlify** — 同上，零配置即可部署

## 技术栈

- [Astro 6](https://astro.build) — 静态站点生成器
- Markdown + Content Collections — 内容管理
- 纯 CSS — 无框架依赖，手写样式
