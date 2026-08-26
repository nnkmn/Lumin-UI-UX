# 组件文档

## Button 按钮

### 概述

按钮遵循 Magnetic Hover 和 Button-in-Button 设计模式。

### 基础用法

```html
<button class="px-btn">默认按钮</button>
<button class="px-btn px-btn--primary">主要按钮</button>
<button class="px-btn px-btn--secondary">次要按钮</button>
<button class="px-btn px-btn--destructive">危险按钮</button>
<button class="px-btn px-btn--icon">I</button>
```

### 尺寸

```html
<button class="px-btn px-btn--sm">小按钮</button>
<button class="px-btn">默认按钮</button>
<button class="px-btn px-btn--lg">大按钮</button>
```

### 状态

```html
<button class="px-btn px-btn--primary" disabled>禁用按钮</button>
```

### 变体说明

| 变体 | 用途 | 特性 |
|------|------|------|
| `px-btn--primary` | 主要操作 | Button-in-Button 高光, 渐变背景, 药丸圆角 |
| `px-btn--secondary` | 次要操作 | 透明背景 + 边框, 药丸圆角 |
| `px-btn--destructive` | 危险操作 | 红色边框 + 文字 |
| `px-btn--icon` | 图标按钮 | 36x36px 正方形 |

### 最佳实践

- 每个视图最多一个 Primary 按钮
- 按钮文字不超过 4 个汉字
- 使用 loading 状态表示异步操作

---

## Input 输入框

### 基础用法

```html
<input class="px-input" placeholder="请输入..." />
```

### 状态

```html
<input class="px-input px-input--error" value="错误内容" />
<input class="px-input" disabled value="禁用状态" />
```

---

## Card 卡片

### 基础用法

```html
<div class="px-card">
  <div class="px-card__inner">卡片内容</div>
</div>
```

### 变体

| 变体 | 用途 |
|------|------|
| `px-card` | 标准卡片 (Double-Bezel) |
| `px-card--subtle` | 轻量卡片 |
| `px-card--double` | 完整双层卡片 |
| `px-card--hoverable` | 可悬浮卡片 |

---

## Toggle 开关

```html
<label class="px-toggle">
  <input type="checkbox" />
  <span class="px-toggle__slider"></span>
</label>
```

---

## Badge 徽章

```html
<span class="px-badge px-badge--primary">主要</span>
<span class="px-badge px-badge--success">成功</span>
<span class="px-badge px-badge--warning">警告</span>
<span class="px-badge px-badge--error">错误</span>
<span class="px-badge px-badge--info">信息</span>
<span class="px-badge px-badge--gradient">渐变</span>
```

### 尺寸

```html
<span class="px-badge px-badge--primary px-badge--sm">小</span>
<span class="px-badge px-badge--primary">默认</span>
<span class="px-badge px-badge--primary px-badge--lg">大</span>
```

### 脉冲徽章

```html
<span class="px-badge px-badge--error px-badge--pulse">3</span>
```

---

## Progress 进度条

```html
<div class="px-progress">
  <div class="px-progress__bar" style="width: 60%"></div>
</div>
```

### 尺寸

```html
<div class="px-progress px-progress--sm">...</div>
<div class="px-progress">...</div>
<div class="px-progress px-progress--lg">...</div>
```

### 条纹动画

```html
<div class="px-progress px-progress--striped">
  <div class="px-progress__bar" style="width: 45%"></div>
</div>
```

### 不定态

```html
<div class="px-progress px-progress--indeterminate">
  <div class="px-progress__bar"></div>
</div>
```

---

## Skeleton 骨架屏

```html
<div class="px-skeleton px-skeleton--text"></div>
<div class="px-skeleton px-skeleton--circle"></div>
<div class="px-skeleton px-skeleton--rectangle"></div>
```

---

## Modal 弹窗

```html
<div class="px-modal-overlay open">
  <div class="px-modal px-modal--md">
    <div class="px-modal__header">
      <h2>标题</h2>
    </div>
    <div class="px-modal__body">
      内容
    </div>
    <div class="px-modal__footer">
      <button class="px-btn px-btn--secondary">取消</button>
      <button class="px-btn px-btn--primary">确认</button>
    </div>
  </div>
</div>
```

### 尺寸

| 变体 | 宽度 |
|------|------|
| `px-modal--sm` | 400px |
| `px-modal--md` | 560px |
| `px-modal--lg` | 720px |
| `px-modal--xl` | 900px |

---

## Toast 轻提示

```html
<div class="px-toast-container">
  <div class="px-toast px-toast--success">
    <div class="px-toast__content">
      <div class="px-toast__title">成功</div>
      <div class="px-toast__message">操作已完成</div>
    </div>
    <span class="px-toast__close">X</span>
  </div>
</div>
```

### 类型

| 变体 | 用途 |
|------|------|
| `px-toast--success` | 成功提示 |
| `px-toast--warning` | 警告提示 |
| `px-toast--error` | 错误提示 |
| `px-toast--info` | 信息提示 |

---

## Select 选择器

```html
<div class="px-select">
  <button class="px-select__trigger">选择选项</button>
  <span class="px-select__arrow">v</span>
  <div class="px-select__dropdown">
    <div class="px-select__option selected">选项 1</div>
    <div class="px-select__option">选项 2</div>
    <div class="px-select__option">选项 3</div>
  </div>
</div>
```
