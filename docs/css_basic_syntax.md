# 基本语法

## 注释

```
/* ... */
```


## 选择器

### 元素选择器

######  

|用法示例        |含义                     |
|---------------|---------------------------|
|h1             |所有h1元素                 |
|h1, h2         |所有h1元素和h2元素           |


### 类选择器

示例：针对类中的p元素设置样式

```css
p.greentea {
	color: green;
}
```

```html
<p class="greentea">
</p>
```

示例：针对类中的所有元素设置样式

```css
.greentea {
	color: green;
}
```


### id选择器

一个元素不能有多个id，多个元素也不能有相同的id。

示例：针对id为footer的任意元素设置样式

```css
#footer {
  color: red;
}
```

示例：针对id为footer的p元素设置样式

```css
p#footer {
  color: red;
}
```






