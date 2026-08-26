# 动效规范

## 缓动曲线

Lumin 使用 Quart-out 物理缓动，创造自然的运动感。

### 核心原则

- **入场** - ease-out (减速停止，自然感)
- **离场** - ease-in (加速消失)
- **切换** - ease-in-out (平滑往返)

### 禁止使用的缓动

- linear
- ease
- bounce
- elastic

### 缓动曲线

```css
--ease-out-quart: cubic-bezier(0.25, 1, 0.5, 1);
--ease-in-quart: cubic-bezier(0.7, 0, 0.84, 0);
--ease-in-out-quart: cubic-bezier(0.65, 0, 0.35, 1);
```

---

## 过渡时间

| 名称 | 时间 | 用途 |
|------|------|------|
| fast | 120ms | 微交互 (hover, focus) |
| normal | 250ms | 状态切换 |
| slow | 400ms | 页面过渡 |

---

## 关键帧动画

### 基础动画

| 动画 | 用途 |
|------|------|
| `fade-in` | 淡入 |
| `fade-out` | 淡出 |
| `slide-up` | 上滑入 (translateY 12px) |
| `slide-down` | 下滑入 (translateY -8px) |
| `slide-left` | 左滑入 (translateX 12px) |
| `slide-right` | 右滑入 (translateX -12px) |
| `scale-in` | 缩放进入 (scale 0.96) |
| `scale-out` | 缩放退出 (scale 0.96) |

### 反馈动画

| 动画 | 用途 |
|------|------|
| `shake` | 抖动反馈 (错误提示) |
| `bounce` | 弹跳 (下载/分享) |
| `pulse` | 脉冲呼吸 |
| `pulse-green` | 联网状态指示 |
| `badge-pulse` | 通知红点 |

### 加载动画

| 动画 | 用途 |
|------|------|
| `spin` | 旋转 |
| `dots` | 加载点 |
| `shimmer` | 骨架屏闪烁 |
| `progress-stripes` | 进度条条纹 |
| `indeterminate` | 不定进度条 |
| `cursor-blink` | 光标闪烁 |

### 通知动画

| 动画 | 用途 |
|------|------|
| `slide-in-right` | 通知卡片侧滑入 |
| `slide-out-right` | 通知卡片侧滑出 |
| `slide-down-sm` | 微下滑入场 |
| `modal-in` | 模态框弹入 |
| `modal-out` | 模态框弹出 |
| `overlay-in` | 遮罩层淡入 |
| `overlay-out` | 遮罩层淡出 |

---

## 交互模式

### Magnetic Hover (磁性悬浮)

悬浮时产生微妙抬升感，按下时回弹。

```css
.hover-lift:hover {
  transform: translateY(-1px);
  transition: transform var(--transition-fast);
}

.hover-lift:active {
  transform: translateY(0) scale(0.98);
}
```

### Button-in-Button (内部高光)

按钮内部创建顶部高光渐变。

```css
.px-btn--primary::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 50%;
  background: linear-gradient(180deg, oklch(100% 0 0 / 0.12) 0%, transparent 100%);
}
```

### 页面过渡

```css
.page-enter-from {
  opacity: 0;
  transform: translateY(8px);
}

.page-leave-to {
  opacity: 0;
  transform: translateY(-4px);
}
```

---

## GPU 加速

```css
.gpu-accelerated {
  will-change: transform, opacity;
  transform: translateZ(0);
}
```

---

## 无障碍支持

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```
