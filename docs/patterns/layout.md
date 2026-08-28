# 布局模式

## 应用壳布局

标准桌面应用布局，包含标题栏、侧边栏和主内容区。

```html
<div class="lumin-app">
  <header class="lumin-titlebar">
    <span class="lumin-titlebar__brand">App Name</span>
    <div class="lumin-titlebar__controls">
      <button class="lumin-wc-btn lumin-wc-btn--minimize">-</button>
      <button class="lumin-wc-btn lumin-wc-btn--maximize">[]</button>
      <button class="lumin-wc-btn lumin-wc-btn--close">X</button>
    </div>
  </header>
  <div class="lumin-app__body">
    <div class="lumin-app__bg"></div>
    <div class="lumin-app__overlay"></div>
    <aside class="lumin-sidebar">
      <nav class="lumin-sidebar__nav">
        <button class="lumin-nav-icon active">
          <span>H</span>
          <span class="nav-icon-label">首页</span>
        </button>
      </nav>
      <div class="lumin-sidebar__content">
        <div class="lumin-sidebar__menu">
          <div class="lumin-nav-group__title">导航</div>
          <button class="lumin-nav-item active">首页</button>
          <button class="lumin-nav-item">设置</button>
        </div>
        <div class="lumin-sidebar__footer">
          版本信息
        </div>
      </div>
    </aside>
    <main class="lumin-main">
      <div class="lumin-content">
        页面内容
      </div>
    </main>
  </div>
</div>
```

### 结构说明

```
.lumin-app (flex column, 100vh)
+-- .lumin-titlebar (44px, glass blur)
+-- .lumin-app__body (flex, flex: 1)
    +-- .lumin-app__bg (背景图层)
    +-- .lumin-app__overlay (颜色叠加)
    +-- .lumin-sidebar (280px, Double-Bezel)
    |   +-- .lumin-sidebar__nav (52px 图标栏)
    |   +-- .lumin-sidebar__content
    |       +-- .lumin-sidebar__menu
    |       +-- .lumin-sidebar__footer
    +-- .lumin-main (flex: 1, glass 背景纹理)
        +-- .lumin-content
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
<div class="lumin-bento">
  <div class="lumin-card lumin-bento__item--span-2">大卡片</div>
  <div class="lumin-card">小卡片</div>
  <div class="lumin-card">小卡片</div>
  <div class="lumin-card lumin-bento__item--span-3">超大卡片</div>
  <div class="lumin-card lumin-bento__item--row-2">高卡片</div>
</div>
```

### 跨列/跨行

| 类名 | 效果 |
|------|------|
| `lumin-bento__item--span-2` | 跨 2 列 |
| `lumin-bento__item--span-3` | 跨 3 列 |
| `lumin-bento__item--span-4` | 跨 4 列 |
| `lumin-bento__item--row-2` | 跨 2 行 |

---

## 卡片网格

自动填充的卡片网格。

```html
<div class="lumin-card-grid">
  <div class="lumin-card">卡片 1</div>
  <div class="lumin-card">卡片 2</div>
  <div class="lumin-card">卡片 3</div>
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
  .lumin-sidebar {
    width: 72px;
    min-width: 72px;
  }
  .lumin-sidebar__content { display: none; }
  .lumin-content { padding: var(--space-lg); }
  .lumin-grid--2, .lumin-grid--3, .lumin-grid--4 { grid-template-columns: 1fr; }
  .lumin-bento { grid-template-columns: repeat(2, 1fr); }
}

@media (max-width: 640px) {
  .lumin-titlebar { height: 40px; padding: 0 10px; }
  .lumin-bento { grid-template-columns: 1fr; }
}
```

---

## 预设布局

### 单栏布局

```html
<div class="lumin-layout-single">
  <main class="lumin-layout-single__main">内容</main>
</div>
```

### 两栏布局

```html
<div class="lumin-layout-two-column">
  <aside class="lumin-layout-two-column__sidebar">侧栏</aside>
  <main class="lumin-layout-two-column__main">内容</main>
</div>
```

### 三栏布局

```html
<div class="lumin-layout-three-column">
  <aside class="lumin-layout-three-column__left">左栏</aside>
  <main class="lumin-layout-three-column__center">内容</main>
  <aside class="lumin-layout-three-column__right">右栏</aside>
</div>
```
