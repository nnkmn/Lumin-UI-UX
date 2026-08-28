# Lumin UI/UX

> 现代、精致、沉浸式的视觉设计系统 | 玻璃态 + 微色调中性色 | 纯 CSS 零依赖

**[在线预览](https://luminuiux.linpork.top/)**

---

## 从 Pixel UI 重构而来

本项目是对 [Pixel UI](https://github.com/nnkmn/Pixel-UI) 的完全重构。

### 变更说明

| 项目 | Pixel UI | Lumin UI/UX |
|------|----------|-------------|
| **设计风格** | 像素风 (Pixel Art) | 玻璃态 (Glass Morphism) |
| **色彩系统** | RGB/HEX | OKLCH 色彩空间 |
| **圆角系统** | 0px 或极小值 | squircle 偏好 (4px ~ 28px) |
| **阴影系统** | 硬阴影 (无 blur) | 柔和环境阴影 |
| **动效系统** | step-end 复古动画 | Quart-out 物理缓动 |
| **字体系统** | 像素字体 (Press Start 2P) | 系统原生字体栈 |
| **组件前缀** | `pg-` / `pm-` / `pc-` | `lumin-` |
| **主题系统** | 简单暗色模式 | dark/light/auto + 8 个预设 |

### 重构目标

- **从像素风转向现代设计** - 去掉像素风格，采用更精致、专业的视觉语言
- **引入设计系统思维** - 建立完整的设计令牌体系，支持主题定制和扩展
- **提升交互体验** - 引入 Double-Bezel、Button-in-Button、Magnetic Hover 等高级设计模式
- **增强无障碍支持** - 支持 `prefers-reduced-motion`、高对比度模式、ARIA 角色
- **框架无关** - 纯 CSS 实现，可适配任何前端框架

---

## 设计理念

**Lumin** 是一种现代、精致、沉浸式的视觉设计语言，专为桌面应用设计。

### 设计哲学

- **克制** (Restrained) - 避免过度装饰，保持界面简洁
- **深度** (Depth) - 通过层次和阴影创造空间感
- **沉浸** (Immersive) - 让用户专注于内容而非界面

### 三大设计模式

| 模式 | 说明 |
|------|------|
| **Double-Bezel** | 卡片使用 `::before` 伪元素创建外层边框壳，营造精致的嵌套层次感 |
| **Button-in-Button** | 主按钮内部使用 `::before` 伪元素创建顶部高光渐变，模拟玻璃质感 |
| **Magnetic Hover** | 导航项和按钮在 hover 时产生微妙抬升，按下时回弹，创造物理交互感 |

---

## 核心特性

- **OKLCH 色彩空间** - 更均匀的感知亮度和更好的色彩过渡
- **CSS 变量驱动** - 改几个变量换整套皮肤
- **亮/暗主题切换** - `data-theme="dark"` 一行搞定
- **Quart-out 物理缓动** - 自然的减速停止感
- **Glass Morphism** - 毛玻璃效果，配合半透明背景色
- **4px 间距系统** - 7 级间距，从 4px 到 48px
- **squircle 圆角** - 8 级圆角，从 4px 到 9999px
- **15 种关键帧动画** - 淡入、滑入、缩放、脉冲、抖动等
- **无障碍支持** - `prefers-reduced-motion`、高对比度模式、ARIA 角色

---

## 快速开始

```html
<!-- 1. 引入样式 -->
<link rel="stylesheet" href="src/styles/tokens.scss">
<link rel="stylesheet" href="src/styles/global.scss">
<link rel="stylesheet" href="src/styles/controls.scss">
<link rel="stylesheet" href="src/styles/animations.scss">
<link rel="stylesheet" href="src/styles/app.scss">

<!-- 2. 设置主题 -->
<html data-theme="dark">

<!-- 3. 使用组件 -->
<button class="lumin-btn lumin-btn--primary">主要按钮</button>
<div class="lumin-card">卡片内容</div>
<input class="lumin-input" placeholder="输入..." />
```

---

## 文件结构

```
Lumin-UI-UX/
├── index.html                    # 入口 HTML
├── src/
│   ├── main.ts                   # 入口文件
│   └── styles/
│       ├── tokens.scss           # 设计令牌 (色彩/间距/圆角/动效/字体/Z-index)
│       ├── global.scss           # 全局重置 (滚动条/焦点环/选区/无障碍)
│       ├── controls.scss         # 组件库 (Card/Button/Input/Toggle/Badge/Progress/Skeleton/Select/Modal/Toast)
│       ├── animations.scss       # 动画库 (15种关键帧 + 工具类 + 延迟 + GPU加速)
│       ├── app.scss              # 布局 (Titlebar/Sidebar/Main/Bento Grid/响应式)
│       └── themes/
│           └── light.scss        # 亮色主题
├── docs/
│   ├── design-principles.md      # 设计原则
│   ├── best-practices.md         # 最佳实践
│   ├── components/
│   │   └── index.md              # 组件文档
│   ├── patterns/
│   │   ├── layout.md             # 布局模式
│   │   ├── motion.md             # 动效规范
│   │   └── theme.md              # 主题系统
│   └── reference/
│       ├── tokens.md             # 设计令牌参考
│       └── utilities.md          # CSS 工具类参考
├── .gitignore
├── LICENSE
└── README.md
```

---

## 设计令牌

### 色彩系统 (OKLCH)

```css
/* 暗色主题 */
--lumin-bg-primary: oklch(12% 0.006 252);
--lumin-primary: oklch(65% 0.19 252);

/* 亮色主题 */
--lumin-bg-primary: oklch(99% 0.002 252);
--lumin-primary: oklch(52% 0.21 252);
```

### 间距系统 (4px 基准)

```css
--lumin-space-xs: 4px;
--lumin-space-sm: 8px;
--lumin-space-md: 12px;
--lumin-space-lg: 16px;
--lumin-space-xl: 24px;
--lumin-space-2xl: 32px;
--lumin-space-3xl: 48px;
```

### 圆角系统 (squircle 偏好)

```css
--lumin-radius-xs: 4px;
--lumin-radius-sm: 6px;
--lumin-radius-md: 10px;
--lumin-radius-lg: 16px;
--lumin-radius-xl: 20px;
--lumin-radius-2xl: 28px;
--lumin-radius-full: 9999px;
```

### 动效系统 (Quart-out)

```css
--lumin-ease-out-quart: cubic-bezier(0.25, 1, 0.5, 1);
--lumin-transition-fast: 120ms;
--lumin-transition-normal: 250ms;
--lumin-transition-slow: 400ms;
```

---

## 组件列表

| 分类 | 组件 |
|------|------|
| 基础 | Button (Primary/Secondary/Destructive/Icon), Input, Select |
| 表单 | Toggle |
| 布局 | Card (Standard/Subtle/Double), Card Grid |
| 反馈 | Modal, Toast, Progress, Skeleton, Badge |
| 导航 | Nav Icon, Nav Item, Nav Group |

---

## 主题系统

支持三种主题模式：

| 模式 | 说明 |
|------|------|
| `dark` | 暗色主题 (默认) |
| `light` | 亮色主题 |
| `auto` | 跟随系统偏好 |

```html
<html data-theme="dark">
<html data-theme="light">
<html data-theme="auto">
```

### 主题预设

内置 8 个主题预设，基于品牌色色相动态生成：

| 预设 | 色相 | 说明 |
|------|------|------|
| indigo | 252 | 靛青 (默认) |
| teal | 175 | 深青 |
| coral | 15 | 珊瑚 |
| amber | 75 | 琥珀 |
| emerald | 142 | 翠绿 |
| sky | 220 | 天蓝 |
| violet | 280 | 紫罗兰 |
| rose | 340 | 玫瑰 |

---

## 无障碍支持

- `:focus-visible` 全局 2px accent 色 outline + 2px offset
- `@media (prefers-reduced-motion: reduce)` 全面禁用动画
- ARIA 角色：`role="dialog"`, `role="status"`, `role="alertdialog"`
- 高对比度模式支持
- 减少透明度模式支持

---

## 浏览器支持

- Chrome / Edge 88+
- Firefox 78+
- Safari 14+

---

## License

[MIT](./LICENSE)
