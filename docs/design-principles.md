# Lumin 设计原则

## 核心理念

Lumin 是一种现代、精致、沉浸式的视觉设计语言，专为桌面应用设计。

### 设计哲学

- **克制** (Restrained) - 避免过度装饰，保持界面简洁
- **深度** (Depth) - 通过层次和阴影创造空间感
- **沉浸** (Immersive) - 让用户专注于内容而非界面

---

## 色彩系统 (OKLCH)

使用 OKLCH 色彩空间，提供更均匀的感知亮度和更好的色彩过渡。

```css
oklch(Lightness Chroma Hue)
```

- **品牌色相**: hue: 252 (Sky Blue)
- **中性色**: 含微量 chroma 朝向品牌蓝，创造统一视觉感受

### 暗色主题

```css
--bg-primary: oklch(12% 0.006 252);
--bg-secondary: oklch(15.5% 0.007 252);
--bg-tertiary: oklch(18.5% 0.007 252);
--primary: oklch(65% 0.19 252);
```

### 亮色主题

```css
--bg-primary: oklch(99% 0.002 252);
--bg-secondary: oklch(96.5% 0.003 252);
--bg-tertiary: oklch(94% 0.004 252);
--primary: oklch(52% 0.21 252);
```

---

## 三大设计模式

### 1. Double-Bezel (双层边框)

卡片和面板使用 `::before` 伪元素创建外层边框壳，元素本体作为内核，营造精致的嵌套层次感。

```css
.px-card {
  position: relative;
  background: var(--bg-secondary);
  border-radius: var(--radius-lg);
  box-shadow: inset 0 1px 1px oklch(100% 0 0 / 0.06);
}

.px-card::before {
  content: '';
  position: absolute;
  inset: -1px;
  background: var(--border-color-light);
  border-radius: calc(var(--radius-lg) + 1px);
  z-index: -1;
  pointer-events: none;
}
```

### 2. Button-in-Button (按钮内按钮)

主按钮内部使用 `::before` 伪元素创建顶部高光渐变，模拟玻璃质感。

```css
.px-btn--primary {
  position: relative;
  overflow: hidden;
}

.px-btn--primary::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 50%;
  background: linear-gradient(
    180deg,
    oklch(100% 0 0 / 0.12) 0%,
    transparent 100%
  );
  pointer-events: none;
}
```

### 3. Magnetic Hover (磁性悬浮)

导航项和按钮在 hover 时产生微妙抬升，按下时回弹，创造物理交互感。

```css
.px-btn:hover {
  transform: translateY(-1px);
}

.px-btn:active {
  transform: translateY(0) scale(0.98);
}
```

---

## 玻璃态效果 (Glass Morphism)

使用 `backdrop-filter` 创建毛玻璃效果，配合半透明背景色。

```css
.px-sidebar::before {
  background: var(--glass-sidebar);
  backdrop-filter: blur(16px) saturate(140%);
  -webkit-backdrop-filter: blur(16px) saturate(140%);
}

.px-titlebar {
  background: var(--glass-titlebar);
  backdrop-filter: blur(20px) saturate(180%);
}
```

---

## 动效系统

### Quart-out 物理缓动

- **入场**: ease-out (减速停止，自然感)
- **离场**: ease-in (加速消失)
- **切换**: ease-in-out (平滑往返)

**禁止**: linear / ease / bounce / elastic

```css
--ease-out-quart: cubic-bezier(0.25, 1, 0.5, 1);
--ease-in-quart: cubic-bezier(0.7, 0, 0.84, 0);
--ease-in-out-quart: cubic-bezier(0.65, 0, 0.35, 1);

--transition-fast: 120ms var(--ease-out-quart);
--transition-normal: 250ms var(--ease-out-quart);
--transition-slow: 400ms var(--ease-out-quart);
```

---

## 无障碍设计

- `:focus-visible` 全局 2px accent 色 outline + 2px offset
- `@media (prefers-reduced-motion: reduce)` 全面禁用动画
- ARIA 角色：`role="dialog"`, `role="status"`, `role="alertdialog"`
- 高对比度模式支持
- 减少透明度模式支持

---

## 参考来源

- Impeccable 7 域 (typography/color/spatial/motion/interaction/responsive/ux-writing)
- High-End Visual Design (Double-Bezel / Button-in-Button / Magnetic Hover)
