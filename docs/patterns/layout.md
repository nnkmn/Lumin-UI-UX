# 布局模式

## 应用壳布局

标准桌面应用布局，包含标题栏、侧边栏和主内容区。

```html
<div class="px-app">
  <header class="px-titlebar">
    <span class="px-titlebar__brand">App Name</span>
    <div class="px-titlebar__controls">
      <button class="px-wc-btn px-wc-btn--minimize">-</button>
      <button class="px-wc-btn px-wc-btn--maximize">[]</button>
      <button class="px-wc-btn px-wc-btn--close">X</button>
    </div>
  </header>
  <div class="px-app__body">
    <div class="px-app__bg"></div>
    <div class="px-app__overlay"></div>
    <aside class="px-sidebar">
      <nav class="px-sidebar__nav">
        <button class="px-nav-icon active">
          <span>H</span>
          <span class="nav-icon-label">首页</span>
        </button>
      </nav>
      <div class="px-sidebar__content">
        <div class="px-sidebar__menu">
          <div class="px-nav-group__title">导航</div>
          <button class="px-nav-item active">首页</button>
          <button class="px-nav-item">设置</button>
        </div>
        <div class="px-sidebar__footer">
          版本信息
        </div>
      </div>
    </aside>
    <main class="px-main">
      <div class="px-content">
        页面内容
      </div>
    </main>
  </div>
</div>
```

### 结构说明

```
.px-app (flex column, 100vh)
+-- .px-titlebar (44px, glass blur)
+-- .px-app__body (flex, flex: 1)
    +-- .px-app__bg (背景图层)
    +-- .px-app__overlay (颜色叠加)
    +-- .px-sidebar (280px, Double-Bezel)
    |   +-- .px-sidebar__nav (52px 图标栏)
    |   +-- .px-sidebar__content
    |       +-- .px-sidebar__menu
    |       +-- .px-sidebar__footer
    +-- .px-main (flex: 1, glass 背景纹理)
        +-- .px-content
```

### 标题栏

- 高度: 44px
- 玻璃态: `backdrop-filter: blur(20px) saturate(180%)`
- 品牌色呼吸感: 右上角径向辉光
- 平台感知: macOS 红绿灯 / Windows 矩形按钮

### 侧边栏

- 宽度: 280px (可折叠到 72px)
- 图标栏: 52px
- 玻璃态: `backdrop-filter: blur(16px) saturate(140%)`
- Double-Bezel: `::before` 伪元素创建玻璃底板

### 主内容区

- 玻璃态: `backdrop-filter: blur(8px) saturate(100%)`
- 自定义滚动条: 6px 宽度
- 最大宽度: 1200px (居中)

---

## Bento Grid 布局

不对称网格布局，用于首页仪表板。

```html
<div class="px-bento">
  <div class="px-card px-bento__item--span-2">大卡片</div>
  <div class="px-card">小卡片</div>
  <div class="px-card">小卡片</div>
  <div class="px-card px-bento__item--span-3">超大卡片</div>
  <div class="px-card px-bento__item--row-2">高卡片</div>
</div>
```

### 跨列/跨行

| 类名 | 效果 |
|------|------|
| `px-bento__item--span-2` | 跨 2 列 |
| `px-bento__item--span-3` | 跨 3 列 |
| `px-bento__item--span-4` | 跨 4 列 |
| `px-bento__item--row-2` | 跨 2 行 |

---

## 卡片网格

自动填充的卡片网格。

```html
<div class="px-card-grid">
  <div class="px-card">卡片 1</div>
  <div class="px-card">卡片 2</div>
  <div class="px-card">卡片 3</div>
</div>
```

---

## 响应式断点

| 断点 | 宽度 | 说明 |
|------|------|------|
| sm | 640px | 手机 |
| md | 768px | 平板 |
| lg | 1024px | 小桌面 |
| xl | 1280px | 大桌面 |

### 响应式行为

```css
@media (max-width: 768px) {
  .px-sidebar {
    width: 72px;
    min-width: 72px;
  }
  .px-sidebar__content { display: none; }
  .px-content { padding: var(--space-lg); }
  .px-grid--2, .px-grid--3, .px-grid--4 { grid-template-columns: 1fr; }
  .px-bento { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 640px) {
  .px-titlebar { height: 40px; padding: 0 10px; }
  .px-bento { grid-template-columns: 1fr; }
}
```

---

## 预设布局

### 单栏布局

```html
<div class="px-layout-single">
  <main class="px-layout-single__main">内容</main>
</div>
```

### 两栏布局

```html
<div class="px-layout-two-column">
  <aside class="px-layout-two-column__sidebar">侧栏</aside>
  <main class="px-layout-two-column__main">内容</main>
</div>
```

### 三栏布局

```html
<div class="px-layout-three-column">
  <aside class="px-layout-three-column__left">左栏</aside>
  <main class="px-layout-three-column__center">内容</main>
  <aside class="px-layout-three-column__right">右栏</aside>
</div>
```
