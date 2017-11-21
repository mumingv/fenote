# FAQ

## head元素中能够包含哪些元素？

- meta
- title
- style／link


## 哪些样式能继承，哪些不能继承？

能继承的样式有：

- color (前景色)
- font-family (字体系列)
- font-size (字体大小)
- font-weight (字体粗细)
- font-style (字体样式：是否斜体)
- line-height（行高／行间距）

不能继承的样式有：

- border (边框)


## 应用样式的顺序优先级是什么？

1. 选择器
2. 继承
3. 默认值

如果一个元素被多个类选择器选中，则使用最特定的选择器样式；如果最特定的选择器有多个，则使用样式表中的最后一个最特定的选择器。


## CSS有哪些非选择器规则？

```css
@font-face
@import
@media
```


## 如何清除页面的所有默认样式？

参考：http://meyerweb.com/eric/tools/css/reset/。


