# HTML标签汇总

## a

### 属性

#### 

|属性名称           |属性含义                       |备注               |
|-------------------|-------------------------------|-------------------|
|href               |超链接                         |必要               |
|target             |在新窗口中打开链接             |必要               |
|title              |超链接的描述信息，鼠标悬停时显示的文本|必要               |


### 示例

#### 链接跳转的几种写法

1.链接跳转到URL页面上的'top'目标

```html
<a href="http://www.baidu.com/news/index.html#top">Baidu</a>
```
```html
<a href="http://www.baidu.com/news/#top">Baidu</a>
```

写成下面这样式不对的

```html
<a href="http://www.baidu.com/news#top">Baidu</a>
```

2.链接跳转到当前页面上的'top'目标

```html
<a href="#top">Back to top</a>
```


#### 在新窗口中打开链接

```html
<a target="_blank" href="http://www.baidu.com">Baidu</a>
```


#### 在同一个新窗口中打开多个链接

```html
<a target="searchengine" href="http://www.baidu.com">Baidu</a>
<a target="searchengine" href="http://www.google.com">Google</a>
```


### 说明

1. `<a>`元素可以基于文字、图像(`<img>`是内联元素)和块元素(如：`<p>`和`<blockquote>`)创建链接。


## link

### 属性

#### 

|属性名称           |属性含义                       |备注                   |
|-------------------|-------------------------------|-----------------------|
|type				|外部信息类型 						|可选|
|rel				|指明HTML文件和所连接文件之间的关系	|必要|
|href				|超链接 							|必要|
|media              |媒体查询，即：指定哪些端使用该样式 |可选|

media属性也可以通过css的@media选择器指定。

###  

示例: 给页面增加样式

```html
<link rel="stylesheet" type="text/css" href="lounge.css">
```

示例：媒体类型为打印机时才使用该格式

```html
<link rel="stylesheet" type="text/css" href="lounge.css" media="print">
```

示例：媒体类型为有屏设备且设备宽度不超过480像素时才使用该格式

```html
<link rel="stylesheet" type="text/css" href="lounge.css" media="screen and (max-device-width: 480px)">
```


## img

### 属性

#### 

|属性名称           |属性含义                       |备注                   |
|-------------------|-------------------------------|-----------------------|
|src                |图像位置                       |必要                   |
|alt                |图像无法显示时显示的文字       |必要                   |


### 示例


## table 表格

## caption 表格标题

## tr 表格行

## th 表格头部单元格（表格数据）

## td 表格普通单元格（表格数据）


## article(H5)
## nav(H5)
## header(H5)
## footer(H5)
## time(H5)
## aside(H5)
## section(H5)
## video(H5)



