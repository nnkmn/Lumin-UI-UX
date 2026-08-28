# CSS 工具类参考

## 布局

### Flexbox

| 类名 | 效果 |
|------|------|
| `.lumin-flex` | `display: flex` |
| `.lumin-flex-col` | `flex-direction: column` |
| `.lumin-flex-row` | `flex-direction: row` |
| `.lumin-flex-wrap` | `flex-wrap: wrap` |
| `.lumin-flex-1` | `flex: 1` |
| `.lumin-flex-shrink-0` | `flex-shrink: 0` |

### 对齐

| 类名 | 效果 |
|------|------|
| `.lumin-items-start` | `align-items: flex-start` |
| `.lumin-items-center` | `align-items: center` |
| `.lumin-items-end` | `align-items: flex-end` |
| `.lumin-items-stretch` | `align-items: stretch` |
| `.lumin-justify-start` | `justify-content: flex-start` |
| `.lumin-justify-center` | `justify-content: center` |
| `.lumin-justify-end` | `justify-content: flex-end` |
| `.lumin-justify-between` | `justify-content: space-between` |
| `.lumin-justify-around` | `justify-content: space-around` |

### 间距

| 类名 | 效果 |
|------|------|
| `.lumin-gap-xs` | `gap: 4px` |
| `.lumin-gap-sm` | `gap: 8px` |
| `.lumin-gap-md` | `gap: 12px` |
| `.lumin-gap-lg` | `gap: 16px` |
| `.lumin-gap-xl` | `gap: 24px` |
| `.lumin-gap-2xl` | `gap: 32px` |

### Grid

| 类名 | 效果 |
|------|------|
| `.lumin-grid` | `display: grid` |
| `.lumin-grid--2` | `grid-template-columns: repeat(2, 1fr)` |
| `.lumin-grid--3` | `grid-template-columns: repeat(3, 1fr)` |
| `.lumin-grid--4` | `grid-template-columns: repeat(4, 1fr)` |
| `.lumin-grid--auto-fill` | `grid-template-columns: repeat(auto-fill, minmax(220px, 1fr))` |
| `.lumin-grid--auto-fit` | `grid-template-columns: repeat(auto-fit, minmax(220px, 1fr))` |

### 定位

| 类名 | 效果 |
|------|------|
| `.lumin-relative` | `position: relative` |
| `.lumin-absolute` | `position: absolute` |
| `.lumin-fixed` | `position: fixed` |
| `.lumin-sticky` | `position: sticky` |

### 尺寸

| 类名 | 效果 |
|------|------|
| `.lumin-w-full` | `width: 100%` |
| `.lumin-h-full` | `height: 100%` |
| `.lumin-min-h-screen` | `min-height: 100vh` |

### 溢出

| 类名 | 效果 |
|------|------|
| `.lumin-overflow-hidden` | `overflow: hidden` |
| `.lumin-overflow-auto` | `overflow: auto` |
| `.lumin-overflow-x-auto` | `overflow-x: auto` |
| `.lumin-overflow-y-auto` | `overflow-y: auto` |

### 文本

| 类名 | 效果 |
|------|------|
| `.lumin-text-center` | `text-align: center` |
| `.lumin-text-left` | `text-align: left` |
| `.lumin-text-right` | `text-align: right` |

### 边距

| 类名 | 效果 |
|------|------|
| `.lumin-m-0` | `margin: 0` |
| `.lumin-mx-auto` | `margin-left: auto; margin-right: auto` |
| `.lumin-mt-auto` | `margin-top: auto` |

### 内边距

| 类名 | 效果 |
|------|------|
| `.lumin-p-0` | `padding: 0` |
| `.lumin-px-lg` | `padding-left/right: 16px` |
| `.lumin-py-lg` | `padding-top/bottom: 16px` |

### 显示

| 类名 | 效果 |
|------|------|
| `.lumin-hidden` | `display: none` |
| `.lumin-block` | `display: block` |
| `.lumin-inline-block` | `display: inline-block` |
| `.lumin-inline-flex` | `display: inline-flex` |

### 响应式

| 类名 | 效果 |
|------|------|
| `.lumin-mobile-hidden` | 在移动端隐藏 |
| `.lumin-mobile-block` | 在移动端显示 |
| `.lumin-mobile-flex` | 在移动端flex |

---

## 动画

### 基础动画

| 类名 | 效果 |
|------|------|
| `.animate-fade-in` | 淡入 |
| `.animate-fade-out` | 淡出 |
| `.animate-slide-up` | 上滑入 |
| `.animate-slide-down` | 下滑入 |
| `.animate-slide-left` | 左滑入 |
| `.animate-slide-right` | 右滑入 |
| `.animate-scale-in` | 缩放进入 |
| `.animate-scale-out` | 缩放退出 |

### 状态动画

| 类名 | 效果 |
|------|------|
| `.animate-spin` | 旋转 (1s) |
| `.animate-spin-slow` | 慢旋转 (2s) |
| `.animate-pulse` | 脉冲 |
| `.animate-pulse-green` | 绿色脉冲 |
| `.animate-badge-pulse` | 徽章脉冲 |
| `.animate-shake` | 抖动 |
| `.animate-bounce` | 弹跳 |

### 加载动画

| 类名 | 效果 |
|------|------|
| `.animate-cursor` | 光标闪烁 |
| `.animate-shimmer` | 骨架屏闪烁 |
| `.animate-progress-stripes` | 进度条条纹 |
| `.animate-indeterminate` | 不定进度条 |
| `.animate-dots` | 加载点 |

### 通知动画

| 类名 | 效果 |
|------|------|
| `.animate-slide-in-right` | 右滑入 |
| `.animate-slide-out-right` | 右滑出 |
| `.animate-slide-down-sm` | 微下滑入 |
| `.animate-modal-in` | 模态框弹入 |
| `.animate-modal-out` | 模态框弹出 |
| `.animate-overlay-in` | 遮罩层淡入 |
| `.animate-overlay-out` | 遮罩层淡出 |

### 延迟

| 类名 | 效果 |
|------|------|
| `.animate-delay-1` | 延迟 0.1s |
| `.animate-delay-2` | 延迟 0.2s |
| `.animate-delay-3` | 延迟 0.3s |
| `.animate-delay-4` | 延迟 0.4s |
| `.animate-delay-5` | 延迟 0.5s |
| `.animate-delay-6` ~ `.animate-delay-10` | 延迟 0.6s ~ 1.0s |

### GPU 加速

| 类名 | 效果 |
|------|------|
| `.gpu-accelerated` | `will-change: transform, opacity` |
| `.gpu-transform` | `will-change: transform` |
| `.gpu-opacity` | `will-change: opacity` |
| `.scroll-optimized` | 滚动优化 |

---

## 过渡

| 类名 | 效果 |
|------|------|
| `.transition-none` | 无过渡 |
| `.transition-all` | 全部过渡 |
| `.transition-colors` | 颜色过渡 |
| `.transition-opacity` | 透明度过渡 |
| `.transition-shadow` | 阴影过渡 |
| `.transition-transform` | 变换过渡 |
| `.transition-btn` | 按钮过渡 |
| `.transition-input` | 输入框过渡 |
| `.transition-card` | 卡片过渡 |

---

## 主题

### 背景色

| 类名 | 效果 |
|------|------|
| `.bg-primary` | 主背景 |
| `.bg-secondary` | 次背景 |
| `.bg-tertiary` | 三级背景 |
| `.bg-elevated` | 提升背景 |

### 文字色

| 类名 | 效果 |
|------|------|
| `.text-primary` | 主文字 |
| `.text-secondary` | 次文字 |
| `.text-tertiary` | 三级文字 |
| `.text-muted` | 禁用文字 |
| `.text-inverse` | 反色文字 |

### 边框

| 类名 | 效果 |
|------|------|
| `.border-color` | 边框色 |
| `.border-color-light` | 浅边框色 |

### 状态色

| 类名 | 效果 |
|------|------|
| `.text-success` | 成功文字 |
| `.text-warning` | 警告文字 |
| `.text-error` | 错误文字 |
| `.text-info` | 信息文字 |
| `.bg-success` | 成功背景 |
| `.bg-warning` | 警告背景 |
| `.bg-error` | 错误背景 |
| `.bg-info` | 信息背景 |

### 玻璃态

| 类名 | 效果 |
|------|------|
| `.glass-sidebar` | 侧边栏玻璃态 |
| `.glass-content` | 内容区玻璃态 |
| `.glass-raised` | 提升层玻璃态 |

---

## 交互

### 悬浮效果

| 类名 | 效果 |
|------|------|
| `.hover-lift` | 悬浮抬升 |
| `.press-scale` | 按下缩放 |
| `.hover-lift-press` | 抬升+按下 |
| `.hover-glow` | 悬浮发光 |
| `.hover-border-glow` | 边框发光 |

### 分割线

| 类名 | 效果 |
|------|------|
| `.lumin-divider` | 水平分割线 |
| `.lumin-divider--vertical` | 垂直分割线 |

### 滚动条

| 类名 | 效果 |
|------|------|
| `.lumin-scrollbar-hidden` | 隐藏滚动条 |
| `.lumin-scrollbar-thin` | 细滚动条 |
| `.lumin-scrollbar-thick` | 粗滚动条 |
