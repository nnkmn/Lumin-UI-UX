# 组件文档

## Button 按钮

### 概述

按钮遵循 Magnetic Hover 和 Button-in-Button 设计模式。

### 基础用法

```html
<button class="lumin-btn">默认按钮</button>
<button class="lumin-btn lumin-btn--primary">主要按钮</button>
<button class="lumin-btn lumin-btn--secondary">次要按钮</button>
<button class="lumin-btn lumin-btn--destructive">危险按钮</button>
<button class="lumin-btn lumin-btn--icon">I</button>
```

### 尺寸

```html
<button class="lumin-btn lumin-btn--sm">小按钮</button>
<button class="lumin-btn">默认按钮</button>
<button class="lumin-btn lumin-btn--lg">大按钮</button>
```

### 状态

```html
<button class="lumin-btn lumin-btn--primary" disabled>禁用按钮</button>
```

### 变体说明

| 变体 | 用途 | 特性 |
|------|------|------|
| `lumin-btn--primary` | 主要操作 | Button-in-Button 高光, 渐变背景, 药丸圆角 |
| `lumin-btn--secondary` | 次要操作 | 透明背景 + 边框, 药丸圆角 |
| `lumin-btn--destructive` | 危险操作 | 红色边框 + 文字 |
| `lumin-btn--icon` | 图标按钮 | 36x36px 正方形 |

### 最佳实践

- 每个视图最多一个 Primary 按钮
- 按钮文字不超过 4 个汉字
- 使用 loading 状态表示异步操作

---

## Input 输入框

### 基础用法

```html
<input class="lumin-input" placeholder="请输入..." />
```

### 状态

```html
<input class="lumin-input lumin-input--error" value="错误内容" />
<input class="lumin-input" disabled value="禁用状态" />
```

---

## Card 卡片

### 基础用法

```html
<div class="lumin-card">
  <div class="lumin-card__inner">卡片内容</div>
</div>
```

### 变体

| 变体 | 用途 |
|------|------|
| `lumin-card` | 标准卡片 (Double-Bezel) |
| `lumin-card--subtle` | 轻量卡片 |
| `lumin-card--double` | 完整双层卡片 |
| `lumin-card--hoverable` | 可悬浮卡片 |

---

## Toggle 开关

```html
<label class="lumin-toggle">
  <input type="checkbox" />
  <span class="lumin-toggle__slider"></span>
</label>
```

---

## Badge 徽章

```html
<span class="lumin-badge lumin-badge--primary">主要</span>
<span class="lumin-badge lumin-badge--success">成功</span>
<span class="lumin-badge lumin-badge--warning">警告</span>
<span class="lumin-badge lumin-badge--error">错误</span>
<span class="lumin-badge lumin-badge--info">信息</span>
<span class="lumin-badge lumin-badge--gradient">渐变</span>
```

### 尺寸

```html
<span class="lumin-badge lumin-badge--primary lumin-badge--sm">小</span>
<span class="lumin-badge lumin-badge--primary">默认</span>
<span class="lumin-badge lumin-badge--primary lumin-badge--lg">大</span>
```

### 脉冲徽章

```html
<span class="lumin-badge lumin-badge--error lumin-badge--pulse">3</span>
```

---

## Progress 进度条

```html
<div class="lumin-progress">
  <div class="lumin-progress__bar" style="width: 60%"></div>
</div>
```

### 尺寸

```html
<div class="lumin-progress lumin-progress--sm">...</div>
<div class="lumin-progress">...</div>
<div class="lumin-progress lumin-progress--lg">...</div>
```

### 条纹动画

```html
<div class="lumin-progress lumin-progress--striped">
  <div class="lumin-progress__bar" style="width: 45%"></div>
</div>
```

### 不定态

```html
<div class="lumin-progress lumin-progress--indeterminate">
  <div class="lumin-progress__bar"></div>
</div>
```

---

## Skeleton 骨架屏

```html
<div class="lumin-skeleton lumin-skeleton--text"></div>
<div class="lumin-skeleton lumin-skeleton--circle"></div>
<div class="lumin-skeleton lumin-skeleton--rectangle"></div>
```

---

## Modal 弹窗

```html
<div class="lumin-modal-overlay open">
  <div class="lumin-modal lumin-modal--md">
    <div class="lumin-modal__header">
      <h2>标题</h2>
    </div>
    <div class="lumin-modal__body">
      内容
    </div>
    <div class="lumin-modal__footer">
      <button class="lumin-btn lumin-btn--secondary">取消</button>
      <button class="lumin-btn lumin-btn--primary">确认</button>
    </div>
  </div>
</div>
```

### 尺寸

| 变体 | 宽度 |
|------|------|
| `lumin-modal--sm` | 400px |
| `lumin-modal--md` | 560px |
| `lumin-modal--lg` | 720px |
| `lumin-modal--xl` | 900px |

---

## Toast 轻提示

```html
<div class="lumin-toast-container">
  <div class="lumin-toast lumin-toast--success">
    <div class="lumin-toast__content">
      <div class="lumin-toast__title">成功</div>
      <div class="lumin-toast__message">操作已完成</div>
    </div>
    <span class="lumin-toast__close">X</span>
  </div>
</div>
```

### 类型

| 变体 | 用途 |
|------|------|
| `lumin-toast--success` | 成功提示 |
| `lumin-toast--warning` | 警告提示 |
| `lumin-toast--error` | 错误提示 |
| `lumin-toast--info` | 信息提示 |

---

## Select 选择器

```html
<div class="lumin-select">
  <button class="lumin-select__trigger">选择选项</button>
  <span class="lumin-select__arrow">v</span>
  <div class="lumin-select__dropdown">
    <div class="lumin-select__option selected">选项 1</div>
    <div class="lumin-select__option">选项 2</div>
    <div class="lumin-select__option">选项 3</div>
  </div>
</div>
```
