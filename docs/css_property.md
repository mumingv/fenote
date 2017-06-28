# CSS属性汇总

## 【总结】文本

######  

|属性名称          	|属性含义           |备注               		|
|-------------------|-------------------|---------------------------|
|font-family        |字体系列           |取值示例：sans-serif|
|font-size          |字体大小           ||
|color              |文本颜色           |不会改变链接文本的颜色		|
|font-weight        |字体粗细           ||
|text-decoration	|文本装饰			|如：下划线为underline		|


## 【总结】边框

######  

|属性名称           	|属性含义           	|备注               |
|-------------------|-------------------|-------------------|
|border-bottom      |下边框           	|属性值顺序：with style color|
|background-color   |背景颜色           ||


## @font-face 自定义字体

######  

字体文件格式：

|文件后缀           |含义           	|备注               |
|-------------------|-------------------|-------------------|
|.ttf               |TrueType字体       |IE版本8及以下不可用|
|.otf               |OpenType字体       ||
|.eot               |Embedded OpenType字体|微软IE专用|
|.svg               |SVG字体            ||
|.woff              |Web开放字体格式    |IE版本8及以下不可用|

示例：

```css
@font-face {
  font-family: "Emblema One";
  src: url("http://wickedlysmart.com/hfhtmlcss/chapter8/journal/EmblemaOne-Regular.woff"), 
  url("http://wickedlysmart.com/hfhtmlcss/chapter8/journal/EmblemaOne-Regular.ttf"); 
}
```


## font-family 字体系列

一共有5个字体系列，如下：

|取值           	|含义           	|备注               |
|-------------------|-------------------|-------------------|
|sans-serif         |无衬线字体         |通常用于计算机显示 |
|serif              |衬线字体           |通常用于新闻报纸排版|
|monospace          |等宽字体           |通常用于代码显示   |
|cursive            |类手写字体         |有时用于标题       |
|fantasy            |装饰性字体         |独特风格展现       |

#### 常见sans-serif字体

- Verdana
- Geneva
- Arial
- Arial Black
- Trebuchet MS


#### 常见serif字体

- Times
- Times New Roman
- Georgia


#### 常见monospace字体

- Courier
- Courier New
- Andale Mono


#### 常见cursive字体

- Apple Chancery
- Comic Sans


#### 常见fantacy字体

- LAST NINJA
- Impact


###  

示例：使用sans-serif字体系列

```css
body {
  font-family: Verdana, Geneva, Arial, sans-serif;
}
```

示例：使用monospace字体系列，字体名称中包含括号

```css
body {
  font-family: "Courier New", Courier, monospace;
}
```





