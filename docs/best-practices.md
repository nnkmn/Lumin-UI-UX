# 最佳实践

## 设计原则

### 1. 克制

- 避免过度装饰
- 每个元素都有明确目的
- 留白是设计的一部分

### 2. 一致性

- 使用设计令牌而非硬编码值
- 遵循命名规范
- 保持交互模式一致

### 3. 层次

- 使用文字色阶创建信息层次
- 使用阴影和边框创建空间层次
- 使用动画引导用户注意力

---

## 组件使用

### 按钮

- 每个视图最多一个 Primary 按钮
- 按钮文字简洁明了 (不超过 4 个汉字)
- 使用正确的按钮变体

### 卡片

- 使用 Double-Bezel 效果增强层次
- 保持卡片内容简洁
- 使用适当的间距

### 输入框

- 提供清晰的标签
- 使用 placeholder 作为提示
- 显示验证状态

### 弹窗

- 使用 Teleport 挂载到 body
- 提供 ARIA 无障碍属性
- 支持 ESC 关闭

---

## 性能优化

### 动画

- 使用 `will-change` 提示浏览器
- 避免动画布局属性 (width, height, top, left)
- 使用 `transform` 和 `opacity` 进行动画
- 使用 `.gpu-accelerated` 提升到合成层

### 玻璃态

- 限制 `backdrop-filter` 的使用范围
- 避免在滚动区域使用复杂的玻璃态效果
- 考虑使用伪元素而非直接应用

### 滚动

- 使用虚拟滚动处理长列表
- 使用 `-webkit-overflow-scrolling: touch` 优化移动端
- 隐藏不需要的滚动条

---

## 无障碍

### 焦点管理

- 使用 `:focus-visible` 显示焦点环
- 确保焦点顺序合理
- 提供跳过导航的快捷方式

### 颜色对比

- 确保文字与背景的对比度符合 WCAG AA 标准
- 不仅依赖颜色传达信息
- 支持高对比度模式

### 动画

- 尊重 `prefers-reduced-motion` 设置
- 提供关闭动画的选项
- 避免闪烁内容

### ARIA

- Modal: `role="dialog"` + `aria-modal` + `aria-labelledby`
- Toast: `role="status"` + `aria-live="polite"`
- Confirm: `role="alertdialog"`
- Button: `aria-label` (图标按钮)

---

## 国际化

### 文本

- 预留足够的文本空间
- 支持 RTL 布局
- 使用 ICU 消息格式

### 图标

- 使用通用的图标
- 提供图标文本替代
- 考虑文化差异

---

## 命名规范

### CSS 类名

- 组件: `lumin-{component}`
- 变体: `lumin-{component}--{variant}`
- 元素: `lumin-{component}__{element}`
- 状态: `.open`, `.active`, `.selected`, `.disabled`, `.error`
- 尺寸: `--sm`, `--md`, `--lg`

### CSS 变量

- 设计令牌: `--{category}-{property}`
- 组件变量: `--lumin-{component}-{property}`
- 主题变量: 在 `[data-theme]` 选择器中定义

---

## 文件组织

```
src/
  styles/
    tokens.scss          # 设计令牌
    global.scss          # 全局重置
    vox-controls.scss    # 控件库
    animations.scss      # 动画库
    app.scss            # 应用布局
    themes/
      dark.scss         # 暗色主题
      light.scss        # 亮色主题
  components/
    common/             # 通用组件
      PxButton.vue
      PxInput.vue
      PxCard.vue
      ...
```

### 样式加载顺序

1. tokens (设计令牌)
2. global (全局重置)
3. controls (控件库)
4. animations (动画库)
5. app (应用布局)
6. themes (主题覆盖)
