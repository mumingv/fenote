# [玩转Bootstrap（基础）](http://www.imooc.com/learn/141)

所有示例：[链接](http://123.56.21.232:8252/video/imooc/bootstrap/basic)。

## Bootstrap简介

### Bootstrap简介

Bootstrap是一个前端开发框架，基于HTML5和CSS3。


### Bootstrap到底是什么

略。


### 如何开始使用Bootstrap

1.Bootstrap2支持更广泛的浏览器，但功能不够强大，代码也不够简洁；
2.Bootstrap3放弃了IE7和Firefox3.x版本的支持，对IE8的支持也有限。

<font color="red">
BootStrap中的JS插件依赖于jQuery，因此jQuery要在Bootstrap之前引用。
</font>

示例：[链接](http://123.56.21.232:8252/video/imooc/bootstrap/basic/ch01/03_basic_template.html)。

#### 代码详解

1.在IE浏览器中运行最新的渲染模式

```
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```

2.初始化移动浏览显示，使得显示的窗口大小等于设备的宽度，初始载入时缩放比例为1，也就是不缩放

```
<meta name="viewport" content="width=device-width, initial-scale=1">
```

3.载入Bootstrap的CSS样式

```
<link href="../../../../../bootstrap/css/bootstrap.min.css" rel="stylesheet">
```

4.Bootstrap3不支持IE7，在IE8中引入了下面两个js文件，支持IE9。所以为了支持IE8，需要增加下面的代码。

```
<!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
<!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
<!--[if lt IE 9]>
  <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
  <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
<![endif]-->
```

其中，bootstrap模板为使IE6、7、8版本（IE9以下版本）浏览器兼容html5新增的标签，引入html5shiv.min.js。同理，为使IE6、7、8版本浏览器兼容css3样式，引入respond.min.js。

5.body最后加入Bootstrap和jQuey插件

```
<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
<script src="http://cdn.bootcss.com/jquery/1.12.4/jquery.min.js"></script>
<!-- Include all compiled plugins (below), or include individual files as needed -->
<script src="../../../../../bootstrap/js/bootstrap.min.js"></script>
```

<font color="red">
重要：一定要把css文件放在head中；把js文件放在body的最下面，并且jquery.min.js在前，bootstrap.min.js在后。
</font>


### 基本的HTML模板

略。


### 全局样式

示例：[链接](http://123.56.21.232:8252/video/imooc/bootstrap/basic/ch01/05_reset_css.html)。

全局样式是reset.css。

<font color="red">
Bootstrap基于注重各浏览器原来的表现的思想，不会对原有样式进行完全重置（清零），而是在原有表现的基础之上进行细节优化。
</font>

Bootstrap的一些细节优化点如下：
1. 移除body的margin声明
2. 设置body的背景色为白色
3. 为排版设置了基本的字体、字号和行高
4. 设置全局链接颜色，且当链接处于悬浮“:hover”状态时才会显示下划线样式

<font color="red">
【知识点】jumbotron类表示超大屏幕，示例参考：[链接](http://www.runoob.com/bootstrap/bootstrap-jumbotron.html)。
</font>


## 排版

### 标题

<font color="red">
【知识点】标题<h1>..<h6>分别可以使用<div>的h1..h6类代替。
</font>




