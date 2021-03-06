# [导航条菜单的制作](http://www.imooc.com/learn/6)

所有示例：[链接](http://123.56.21.232:8252/video/imooc/htmlcss/nav_bar/)。

## 垂直菜单的制作

- [站酷 (http://www.zcool.com.cn/)](http://www.zcool.com.cn/)
- [21CN (http://www.21cn.com/)](http://www.21cn.com/)


## 水平菜单的制作

水平菜单是基于垂直菜单，使用float属性制作出来的。


## 圆角菜单的制作

水平菜单是基于水平菜单制作出来的，步骤如下：
1. a标签增加背景色；
2. 首页菜单默认样式改成和a.hover一样；


## 伸缩菜单的制作--改变高度

伸缩菜单是基于圆角菜单制作出来的，步骤如下：
1. 去除圆角背景图；
2. 通过margin-top:-10px;height:40px;line-height:40px;制作向上伸缩效果；

## 伸缩菜单的制作--水平方向

使用Javascript或者jQuery进行伸缩控制。


## 总结：二级菜单下拉列表

<font color="red">
处理思路：去除原有样式 -> 浮动 -> 设置宽度 -> 其他修饰。
</font>


二级菜单下拉列表详细制作步骤如下：

1.去除li标签的样式(list-style-type属性作用于ul或li标签都可以)

```css
ul {
  list-style-type: none;
}
```

2.去除所有元素的边距和填充，并设置页面整体的字体大小

```css
* {
  margin: 0;
  padding: 0;
  font-size: 14px;
}
```
    
3.设置所有li元素的宽度并进行浮动

```css
ul.nav li {
  width: 120px;
  float: left;
}
```

4.设置整个菜单栏的轮廓，包括：宽度、高度、左边距和下边框

```css
ul.nav {
  width: 600px;
  height: 30px;
  margin-left: 50px;
  border-bottom: 5px solid #f60;
}
```

5.设置a元素为块元素，并且设置宽度和高度

<font color="red">说明：设置a元素的宽度和高度之前，必须先将其设置为块元素；因为只有块元素才能设置宽度和高度，而a元素是内联元素。</font>

```css
ul.nav li a {
  display: block;
  width: 120px;
  height: 30px;
}
```

6.将a元素内的文字水平居中对齐(使用text-align属性)，以及垂直居中对齐(使用line-height属性)

```css
ul.nav li a {
  text-align: center;
  line-height: 30px;
}
```

7.去除a元素内文字的下划线

```css
ul.nav li a {
  text-decoration: none;
}
```

8.设置a元素的文本颜色以及背景色

```css
ul.nav li a {
  color: #333;
  background-color: #efefef;
}
```

9.设置子菜单的宽高、背景色，并且将其隐藏

```css
ul.subnav {
  width: 120px;
  height: 0;
  overflow: hidden;
}
ul.subnav li a {
  background-color: #ddd;
}
ul.subnav li a:hover {
  background-color: #efefef;
}
```

10.使用jQuery设置动画效果

```javascript
<script src="http://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
<script type="text/javascript">
$(function() {
  $("li").hover(
    function() {
        $(this).children("ul").stop().animate({"height":"120px"}, 200)
    },
    function() {
        $(this).children("ul").stop().animate({"height":"0px"}, 200)
    }
   )
})
</script>
```








