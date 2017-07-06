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
|div p 			|所有div下的后代p元素			|
|div p span 	|所有级联下的span元素			|
|div>p 			|所有div下的子p元素			|


### 类选择器

类名要以一个字母开头，id名可以以一个数字或字母开头。

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

类名要以一个字母开头，id名可以以一个数字或字母开头。

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


### 伪类选择器

a元素的伪类选择器，有如下5种（建议按这个顺序指定样式）：
- a:link  未访问
- a:visited  已访问
- a:hover  悬停
- a:focus  焦点（使用TAB键触发）
- a:active  鼠标点击按下未抬起

其他伪类选择器有：
- :first-child
- :last-child





