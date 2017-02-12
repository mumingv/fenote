# [搜索框制作](http://www.imooc.com/learn/21)

所有示例：[链接](http://123.56.21.232:8252/video/imooc/js/search_box/index.html)。

## 搜索框制作步骤详解

示例：[链接](http://123.56.21.232:8252/video/imooc/js/search_box/my_search_box.html)。

### HTML框架和内容

#### 1. 使用Sublime的Emmet插件生成HTML框架

方法：输入“!”后按<TAB> 或 <Ctrl + E> 。


#### 2. 构造搜索框

```css
<body>
    <div class="search-box">
        <div class="search-logo"></div>
        <form class="search-form" action="/search" target="_blank">
            <input type="text" class="search-text" name="q" autocomplete="off" />
            <input type="submit" class="search-button" />
        </form>
    </div>
</body>
```

搜索框包含三部分，分别是：
- logo
- 文本框
- 搜索按钮

<font color="red">
文本框的autocomplete="off"用于关闭表单的自动填充功能。
</font>


#### 3. [可选]智能提示动态效果

```
<div class="suggest" id="search-suggest" style="display:none;">
    <ul>
        <li>苹果</li>
        <li>香蕉</li>
        <li>橘子</li>
    </ul>
</div>
```




### CSS样式

#### 1. 清除默认样式并设置页面背景色

```
<style type="text/css">
    * {
        margin: 0;
        padding: 0;
        font-size: 14px;
    }
    body {
        background-color: #fff;
    }
</style>
```


#### 2. 定位搜索框，将其移动到要展示的位置

```css
div.search-box {
    position: absolute;
    top: 150px;
    left: 200px;
}
```

对于定位类型(position)主要有三种：
- 相对定位(relative)：相对于元素本来的位置进行定位
- 绝对定位(absolute): 相对于父元素进行定位
- 固定定位(fixed): 相对于浏览器窗口进行定位


#### 3. 载入logo，即将logo设置为背景色

```css
div.search-logo {
    width: 107px;
    height: 53px;
    background-image: url("image/bf_logo.jpg");
}
```

<font color="red">
由于div.search-logo是个空div，没有大小。所以在设置background-image属性之前一定要先设置div的宽高。
</font>


#### 4. 将search-logo和search-form显示在同一行，使用float属性

```css
div.search-logo {
    float: left;
}
form.search-form {
    float: left;
}
```


#### 5. 设置文本框样式：宽、高、行高、边框、轮廓

```css
input.search-text {
    width: 350px;
    height: 29px;
    line-height: 29px;
    border: 1px solid #aaa;
    outline: none;
}
```

<font color="red">
文本框有默认的轮廓效果，需要显式地去除。
</font>


#### 6. 设置搜索按钮样式：宽、高、背景图片

首先需要去除按钮的默认样式(带有"提交"字样的文字)，通过设置value=""实现。

```
<input type="submit" class="search-button" value="" />
```

去除默认边框并设置宽、高、背景图片。

```css
input.search-button {
    border: 0;
    width: 29px;
    height: 29px;
    background-image: url("image/bf-search-button.png");
}
```


#### 7. 将各元素显示在同一行：浮动、边距、填充

将文本框和搜索按钮显示在同一行。

```css
input.search-text {
    float: left;
}
input.search-button {
    float: left;
}
```

将logo和搜索表单(包含文本框和搜索按钮)显示在同一行。

```css
div.search-logo {
    margin: -8px 5px 0 0;
}
form.search-form {
    padding: 3px;
}
```


#### 8. 将显示的边框包含文本框和按钮

```css
form.search-form {
    border: 1px solid #aaa;
}
input.search-text {
    border: 0;
}
```


#### 9. [可选]智能提示动态效果的样式

```
div.suggest {
    width: 387px;
    background-color: #fff;
    border: 1px solid #999;
}
div.suggest ul {
    list-style: none;
}
div.suggest ul li {
    padding: 3px;
    line-height: 25px;
    cursor: pointer;
}
div.suggest ul li:hover {
    text-decoration: underline;
    background-color: #eee;
}
```

<font color="red">
注意：需要去除ul的样式，使用list-style: none;。
</font>


### JS交互(使用jQuery)


#### 1. 加载jQuery脚本

```javascript
<body>
    ...
    <script src="http://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
</body>
```

<font color="red">
script脚本代码在<body>的最后加载。
</font>


#### 2. [可选]智能提示动态效果的交互

<font color="red">
说明：静态元素使用绑定(bind)，动态元素使用代理(delegate)。
</font>

```javascript
<script>
$(".search-text").bind("keyup", function(){
    var searchText = $(this).val();
    $.get("/video/imooc/js/search_box/index.php?q=" + searchText, function(data) {
        var htmlText = "";
        for (var i = 0; i < data.length; i++) {
            htmlText += "<li>"+data[i]+"</li>";
        }
        $(".suggest>ul").html(htmlText);
        $(".suggest").show().css({
            position: "absolute",
            top: $(".search-form").offset().top + $(".search-form").height() + 7,
            left: $(".search-form").offset().left
        });
    }, "json");
});
$(document).bind("click", function() {
    $(".suggest").hide(); 
});
$(document).delegate("li", "click", function() {
    var keyword = $(this).text();
    location.href = "https://www.baidu.com/s?wd=" + keyword; 
});
</script>
```


## 简单搜索框制作

### 搜索框介绍

搜索框示例：
- http://36kr.com/
- https://www.baidu.com/
- https://www.taobao.com/


### 标签讲解

`<input />`的局限性：其是自闭合标签，不能定义复杂样式的按钮。解决该问题的方法是使用`<button></button>`标签。

三种按钮的表示方法：

```
<input type="button" value="input button" />
<input type="submit" value="submit button" />
<button><img src="image/icon.jpg" width="10px"> this is button</button>
```

`<form></form>`表单需要配合`<input type="submit">`把表单数据提交到服务器，但是不能与`<button></button>`标签配合处理。


## 智能提示搜索框制作


## 淘宝搜索框制作

