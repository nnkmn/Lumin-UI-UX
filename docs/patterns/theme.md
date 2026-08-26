# 主题系统

## 主题模式

支持三种主题模式：

| 模式 | 说明 |
|------|------|
| `dark` | 暗色主题 (默认) |
| `light` | 亮色主题 |
| `auto` | 跟随系统偏好 |

通过 `data-theme` 属性切换：

```html
<html data-theme="dark">
<html data-theme="light">
<html data-theme="auto">
```

---

## 色彩系统 (OKLCH)

使用 OKLCH 色彩空间，提供更均匀的感知亮度。

### 品牌色

品牌色相固定为 `hue: 252` (Sky Blue)。

### 微色调中性色

中性色含有微量 chroma 朝向品牌蓝，创造统一的视觉感受。

---

## 暗色主题

### 背景色阶

中性色含微量蓝调 (hue: 252)。

| 变量 | 值 |
|------|-----|
| `--bg-primary` | `oklch(12% 0.006 252)` |
| `--bg-secondary` | `oklch(15.5% 0.007 252)` |
| `--bg-tertiary` | `oklch(18.5% 0.007 252)` |
| `--bg-elevated` | `oklch(21% 0.007 252)` |

### 文字色阶

| 变量 | 值 |
|------|-----|
| `--text-primary` | `oklch(96% 0.002 252)` |
| `--text-secondary` | `oklch(72% 0.003 252)` |
| `--text-tertiary` | `oklch(54% 0.002 252)` |
| `--text-muted` | `oklch(40% 0.002 252)` |

### 主色

| 变量 | 值 |
|------|-----|
| `--primary` | `oklch(65% 0.19 252)` |
| `--primary-hover` | `oklch(70% 0.17 252)` |

### 玻璃态

| 变量 | 值 |
|------|-----|
| `--glass-sidebar` | `oklch(14% 0.006 252 / 0.78)` |
| `--glass-content` | `oklch(15% 0.006 252 / 0.72)` |
| `--glass-titlebar` | `oklch(9% 0.005 252 / 0.85)` |

---

## 亮色主题

### 背景色阶

暖白中性色。

| 变量 | 值 |
|------|-----|
| `--bg-primary` | `oklch(99% 0.002 252)` |
| `--bg-secondary` | `oklch(96.5% 0.003 252)` |
| `--bg-tertiary` | `oklch(94% 0.004 252)` |
| `--bg-elevated` | `oklch(100% 0 0)` |

### 文字色阶

深色暖灰，保证 WCAG AA 对比度。

| 变量 | 值 |
|------|-----|
| `--text-primary` | `oklch(20% 0.002 252)` |
| `--text-secondary` | `oklch(38% 0.002 252)` |
| `--text-tertiary` | `oklch(52% 0.001 252)` |
| `--text-muted` | `oklch(62% 0.001 252)` |

### 主色

更高饱和度保证白底对比度。

| 变量 | 值 |
|------|-----|
| `--primary` | `oklch(52% 0.21 252)` |
| `--primary-hover` | `oklch(56% 0.19 252)` |

### 玻璃态

白底毛玻璃效果。

| 变量 | 值 |
|------|-----|
| `--glass-sidebar` | `oklch(100% 0 0 / 0.78)` |
| `--glass-content` | `oklch(100% 0 0 / 0.72)` |
| `--glass-titlebar` | `oklch(98% 0.002 252 / 0.85)` |

---

## 主题预设

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

### 预设生成规则

基于色相 (hue) 自动生成完整变量集：

```javascript
function computeThemeVars(hue) {
  return {
    '--primary': `oklch(65% 0.19 ${hue})`,
    '--primary-hover': `oklch(70% 0.17 ${hue})`,
    '--primary-light': `oklch(65% 0.19 ${hue} / 0.12)`,
    '--accent': `oklch(65% 0.19 ${hue})`,
    '--accent-soft': `oklch(65% 0.19 ${hue} / 0.1)`,
    '--gradient-primary': `linear-gradient(135deg, oklch(65% 0.19 ${hue}), oklch(72% 0.15 ${hue}))`,
  };
}
```

---

## 主题管理 API

```javascript
// 设置主题
document.documentElement.setAttribute('data-theme', 'dark');

// 设置预设
const vars = computeThemeVars(252);
Object.entries(vars).forEach(([key, value]) => {
  document.documentElement.style.setProperty(key, value);
});

// 跟随系统
const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
```

---

## 无障碍支持

### 高对比度模式

```css
@media (prefers-contrast: high) {
  [data-theme='dark'] {
    --bg-primary: oklch(0% 0 0);
    --text-primary: oklch(100% 0 0);
    --border-color: oklch(100% 0 0 / 0.5);
  }
}
```

### 减少透明度

```css
@media (prefers-reduced-transparency: reduce) {
  :root {
    --glass-sidebar: var(--bg-secondary);
    --glass-content: var(--bg-secondary);
    --glass-raised: var(--bg-elevated);
  }
}
```
