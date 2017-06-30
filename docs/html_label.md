# HTML标签汇总

## a

### 属性

#### 

|属性名称           |属性含义                       |备注               |
|-------------------|-------------------------------|-------------------|
|href               |超链接                         |必要               |
|target             |在新窗口中打开链接             |必要               |
|title              |超链接的描述信息               |必要               |


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


### 示例: 给页面增加样式

```html
<link rel="stylesheet" type="text/css" href="lounge.css">
```


## img

### 属性

#### 

|属性名称           |属性含义                       |备注                   |
|-------------------|-------------------------------|-----------------------|
|src                |图像位置                       |必要                   |
|alt                |图像无法显示时显示的文字       |必要                   |


### 示例
