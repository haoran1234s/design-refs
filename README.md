# 审美参考库 · Design Refs

> 给前端工程师的国外高质量站点参考清单：66 个参考源、动效技术栈、可直接用的模板，以及一条 6 周落地路线。

**在线访问** → https://haoran1234s.github.io/design-refs/
**旧版存档** → https://haoran1234s.github.io/design-refs/v1.html

## 这是什么

一份用来「练审美」的索引，不是链接大杂烩。所有条目按**用途**分区，每一条都写明「为什么看它、先看哪个部分」，避免在 Awwwards 上漫无目的地刷图。

| 分区 | 内容 |
|---|---|
| 01 Galleries | Godly、Awwwards、SiteInspire、Refero 等筛选标准最严的画廊 |
| 02 Studios | Active Theory、Locomotive、Basement、Lusion 等一线团队官网 |
| 03 Stack | GSAP + ScrollTrigger、Lenis、View Transitions、Three.js 的学习顺序 |
| 04 Templates | Once UI Magic Portfolio、Astro Paper、Fuwari、Astro Nano |
| 05 Basics | Refactoring UI、Practical Typography、网格系统 |
| 06 Plan | 6 周落地路线 + 六个常见坑 |

## 设计参考

这一版是「照着具体站点临摹」的产物，不是凭感觉调的：

- **Basement Studio** —— 主骨架。极细分割线、等宽字体标签、大字号、零图片、全靠 hover 制造反馈。
- **Locomotive** —— 编辑节奏。左侧 sticky 章节栏、遮罩式文字揭示、非对称栅格。
- **Godly** —— 克制。强调色只出现在极少数像素上，其余全部交给排版。

配色从上一版的「纯黑 + 酸性黄绿」（2023 年以来最泛滥的开发者站配色）换成**暖调近黑 `#0b0b09` + 单一朱橙 `#ff4a17`**。

## 交互清单

页面上每个动效都有明确职责，不是装饰：

| 交互 | 解决的问题 |
|---|---|
| 逐行遮罩揭示 | 让长列表有阅读节奏，不一次性糊在屏幕上 |
| 停靠式悬停预览 | 右侧留白接住鼠标反馈，同时**不遮挡正文**；域名标签淡出，由卡片接手 |
| 自定义光标（dot + 拖尾环） | 悬停可点击元素时放大，给出「这里能点」的即时反馈 |
| 跑马灯随滚动加速 | 滚动速度映射到位移速度，是这类站点的标志性细节 |
| 数字滚动（66） | 首屏建立「量」的直觉 |
| 首屏视差 | 标题与栅格不同速度位移，制造纵深 |
| `prefers-reduced-motion` | 系统开启「减少动态效果」时全部关闭 |

## 技术说明

- **纯 HTML + CSS + 原生 JS**，无框架、无打包、无第三方动画库（单文件约 52KB）
- **字体全部自托管**，不走 Google Fonts CDN —— 国内访问 CDN 会被墙，回退到系统字体会直接毁掉版式
  - 中文：Noto Serif SC / Noto Sans SC，用 `fontTools` 按页面实际字符集子集化，686 字 ≈ 287KB
  - 拉丁：Instrument Serif、Inter Tight、JetBrains Mono，共 7 个 woff2 ≈ 150KB
  - 全站字体总计约 450KB
- **零图片**：卡片封面是 `hash(名称)` 生成的 HSL 渐变，同一个站点永远同一个颜色
- 响应式：1440 / 1024 / 390 三档实测，无横向溢出

## 本地运行

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```

直接双击 `index.html` 也能看，但部分浏览器会因 CORS 拒绝加载本地 woff2 字体，建议起本地服务器。

## 部署

GitHub Pages，`main` 分支根目录。`.nojekyll` 已就位（禁用 Jekyll 处理）。

## 备注

清单里的站点均为外链，版权归各自作者所有。文中对技术栈的判断（如 GSAP 插件免费）写于 2026 年，可能随时间变化。
