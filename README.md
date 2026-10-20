# 审美参考库 · Design Refs

> 给前端工程师的国外高质量站点参考清单：66 个参考源、动效技术栈、可直接用的模板，以及一条 6 周落地路线。

**在线访问** → https://haoran1234s.github.io/design-refs/

## 这是什么

一份用来「练审美」的索引，不是链接大杂烩。所有条目按**用途**分区，每一条都写明「为什么看它、先看哪个部分」，避免在 Awwwards 上漫无目的地刷图。

| 分区 | 内容 |
|---|---|
| 基础审美 | Godly、Awwwards、SiteInspire、Refero 等筛选标准最严的画廊 |
| 工作室 | Active Theory、Locomotive、Basement、Lusion 等一线创意团队官网 |
| 动效技术栈 | GSAP + ScrollTrigger、Lenis、View Transitions、Three.js 的学习顺序 |
| 模板 | Once UI Magic Portfolio、Astro Paper、Fuwari、Astro Nano |
| 6 周路线 | 从拆解到上线，每周一个可交付目标 |

## 页面本身的设计

这个页面同时是一份实现示例，打开 DevTools 可以直接拆：

- **暗色底 + 细线栅格**，强调词用宋体衬线做对比，正文用无衬线
- **逐条 reveal**：基于 `IntersectionObserver`，无第三方动画库
- **滚动进度条** + 指针聚光（`radial-gradient` 跟随鼠标）
- **`prefers-reduced-motion` 降级**：系统开启「减少动态效果」时关闭所有位移与视差
- 响应式：桌面双栏 → 移动端单列，导航折叠

## 本地运行

单文件、零构建、零依赖，直接打开即可：

```bash
open index.html        # macOS
start index.html       # Windows
```

需要本地服务器时：

```bash
python -m http.server 8000
```

## 技术说明

- 纯 HTML + CSS + 原生 JS，无框架、无打包步骤
- 字体通过 Google Fonts CDN 加载（Instrument Serif / Inter Tight / JetBrains Mono / Noto Serif SC），离线时回退到系统字体
- 部署：GitHub Pages，`main` 分支根目录

## 备注

清单里的价格、开盘时间等事实性内容来自公开房产平台与官方公告，会随时间变化，以官方公示为准。链接均为外站，版权归各自作者所有。
