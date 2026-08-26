# 设计令牌参考

## 间距系统 (4px 基准)

| 变量 | 值 | 用途 |
|------|-----|------|
| `--space-xs` | 4px | 最小间距 |
| `--space-sm` | 8px | 小间距 |
| `--space-md` | 12px | 中间距 |
| `--space-lg` | 16px | 大间距 |
| `--space-xl` | 24px | 超大间距 |
| `--space-2xl` | 32px | 巨大间距 |
| `--space-3xl` | 48px | 超巨大间距 |

## 圆角系统 (squircle 偏好)

| 变量 | 值 | 用途 |
|------|-----|------|
| `--radius-xs` | 4px | 最小圆角 |
| `--radius-sm` | 6px | 小圆角 |
| `--radius-md` | 10px | 中圆角 |
| `--radius-lg` | 16px | 大圆角 |
| `--radius-xl` | 20px | 超大圆角 |
| `--radius-2xl` | 28px | 巨大圆角 |
| `--radius-full` | 9999px | 药丸形状 |

## 字体系统

### 字体栈

| 变量 | 值 |
|------|-----|
| `--font-sans` | `-apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif` |
| `--font-mono` | `'JetBrains Mono', ui-monospace, monospace` |

### 字号

| 变量 | 值 |
|------|-----|
| `--text-xs` | 11px |
| `--text-sm` | 12px |
| `--text-base` | 13px |
| `--text-lg` | 15px |
| `--text-xl` | 17px |
| `--text-2xl` | 20px |
| `--text-3xl` | 24px |

### 字重

| 变量 | 值 |
|------|-----|
| `--font-normal` | 400 |
| `--font-medium` | 500 |
| `--font-semibold` | 600 |
| `--font-bold` | 700 |

## 动效系统

### 缓动曲线

| 变量 | 值 | 用途 |
|------|-----|------|
| `--ease-out-quart` | `cubic-bezier(0.25, 1, 0.5, 1)` | 入场 |
| `--ease-in-quart` | `cubic-bezier(0.7, 0, 0.84, 0)` | 离场 |
| `--ease-in-out-quart` | `cubic-bezier(0.65, 0, 0.35, 1)` | 切换 |

### 过渡时间

| 变量 | 值 | 用途 |
|------|-----|------|
| `--transition-fast` | 120ms | 微交互 (hover, focus) |
| `--transition-normal` | 250ms | 状态切换 |
| `--transition-slow` | 400ms | 页面过渡 |

## Z-index 层级

| 变量 | 值 | 用途 |
|------|-----|------|
| `--z-base` | 0 | 基础层 |
| `--z-raised` | 1 | 提升层 |
| `--z-above` | 2 | 上方层 |
| `--z-titlebar` | 10 | 标题栏 |
| `--z-float` | 50 | 悬浮层 |
| `--z-dropdown` | 1000 | 下拉菜单 |
| `--z-sticky` | 9000 | 粘性元素 |
| `--z-overlay` | 9999 | 遮罩层 |
| `--z-toast` | 10000 | 提示框 |
| `--z-notification` | 10001 | 通知 |
| `--z-modal` | 10002 | 模态框 |
| `--z-confirm` | 10003 | 确认框 |
| `--z-max` | 99999 | 最高层 |

## 色彩系统 (OKLCH)

### 暗色主题背景

| 变量 | 值 |
|------|-----|
| `--bg-primary` | `oklch(12% 0.006 252)` |
| `--bg-secondary` | `oklch(15.5% 0.007 252)` |
| `--bg-tertiary` | `oklch(18.5% 0.007 252)` |
| `--bg-elevated` | `oklch(21% 0.007 252)` |
| `--bg-input` | `oklch(17% 0.006 252)` |

### 暗色主题文字

| 变量 | 值 |
|------|-----|
| `--text-primary` | `oklch(96% 0.002 252)` |
| `--text-secondary` | `oklch(72% 0.003 252)` |
| `--text-tertiary` | `oklch(54% 0.002 252)` |
| `--text-muted` | `oklch(40% 0.002 252)` |

### 亮色主题背景

| 变量 | 值 |
|------|-----|
| `--bg-primary` | `oklch(99% 0.002 252)` |
| `--bg-secondary` | `oklch(96.5% 0.003 252)` |
| `--bg-tertiary` | `oklch(94% 0.004 252)` |
| `--bg-elevated` | `oklch(100% 0 0)` |
| `--bg-input` | `oklch(100% 0 0)` |

### 亮色主题文字

| 变量 | 值 |
|------|-----|
| `--text-primary` | `oklch(20% 0.002 252)` |
| `--text-secondary` | `oklch(38% 0.002 252)` |
| `--text-tertiary` | `oklch(52% 0.001 252)` |
| `--text-muted` | `oklch(62% 0.001 252)` |

### 主色

| 变量 | 暗色值 | 亮色值 |
|------|--------|--------|
| `--primary` | `oklch(65% 0.19 252)` | `oklch(52% 0.21 252)` |
| `--primary-hover` | `oklch(70% 0.17 252)` | `oklch(56% 0.19 252)` |
| `--primary-light` | `oklch(65% 0.19 252 / 0.12)` | `oklch(52% 0.21 252 / 0.1)` |

### 状态色

| 变量 | 暗色值 | 亮色值 |
|------|--------|--------|
| `--success` | `oklch(68% 0.19 142)` | `oklch(55% 0.19 142)` |
| `--warning` | `oklch(72% 0.17 75)` | `oklch(58% 0.17 75)` |
| `--error` | `oklch(58% 0.24 27)` | `oklch(48% 0.24 27)` |
| `--info` | `oklch(65% 0.19 252)` | `oklch(52% 0.21 252)` |

### 玻璃态

| 变量 | 暗色值 | 亮色值 |
|------|--------|--------|
| `--glass-sidebar` | `oklch(14% 0.006 252 / 0.78)` | `oklch(100% 0 0 / 0.78)` |
| `--glass-content` | `oklch(15% 0.006 252 / 0.72)` | `oklch(100% 0 0 / 0.72)` |
| `--glass-raised` | `oklch(21% 0.007 252 / 0.85)` | `oklch(100% 0 0 / 0.88)` |
| `--glass-titlebar` | `oklch(9% 0.005 252 / 0.85)` | `oklch(98% 0.002 252 / 0.85)` |

### 阴影

| 变量 | 暗色值 | 亮色值 |
|------|--------|--------|
| `--shadow-sm` | `0 1px 3px oklch(0% 0 0 / 0.3)` | `0 1px 3px oklch(0% 0 0 / 0.06)` |
| `--shadow-md` | `0 4px 12px oklch(0% 0 0 / 0.35)` | `0 4px 12px oklch(0% 0 0 / 0.08)` |
| `--shadow-lg` | `0 8px 32px oklch(0% 0 0 / 0.4)` | `0 8px 32px oklch(0% 0 0 / 0.1)` |
| `--shadow-xl` | `0 12px 48px oklch(0% 0 0 / 0.5)` | `0 12px 48px oklch(0% 0 0 / 0.12)` |

### 边框

| 变量 | 暗色值 | 亮色值 |
|------|--------|--------|
| `--border-color` | `oklch(100% 0 0 / 0.08)` | `oklch(0% 0 0 / 0.08)` |
| `--border-color-light` | `oklch(100% 0 0 / 0.05)` | `oklch(0% 0 0 / 0.05)` |
| `--border-strong` | `oklch(100% 0 0 / 0.12)` | `oklch(0% 0 0 / 0.13)` |
