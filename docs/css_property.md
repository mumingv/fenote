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


## background 背景

可以同时指定背景的颜色、图像和重复。这几个参数可以是任意顺序。

###  

```css
background: white url(images/cocktail.gif) repeat-x;
```


## background-color 背景颜色

说明：背景颜色会延伸到内边距和边框（不会延伸到外边距），如果边框是锯齿形的就能够看到背景色。

```css
background-color: #a7cece;
```


## background-image 背景图像

说明：

1. 背景图像会延伸到内边距和边框（不会延伸到外边距），如果边框是锯齿形的就能够看到背景图像；
2. url可以是相对路径，也可以是绝对路径；
3. url不需要加引号；
4. 默认情况下，背景图像是重复的。

```css
background-image: url(images/background.gif);
```


## background-position 背景图像位置

位置可以按照像素、百分数或者关键字来指定。

###  

```css
background-position: top left;
```


## background-repeat 背景图像重复

可能取值：
- no-repeat
- repeat-x
- repeat-y

###  

```css
background-repeat: no-repeat;
```


## border 边框

可以同时指定边框的宽度、样式、颜色。这几个参数可以是任意顺序。

###  

示例：依次指定边框的宽度、样式和颜色

```
border: 1px solid red;
```


## border-width 边框宽度

宽度可以使用px或者关键字（thin, medium, thick）来设置。

###  

```css
border-width: 1px;
```


## border-style 边框样式

常用取值：

- solid 实线
- dotted 点线
- dashed 虚线
- double 双实线
- groove 凹形
- ridge 凸形
- inset 
- outset 

###  

```css
border-style: dashed;
```


## border-color 边框颜色

说明：因为背景颜色会延伸到内边距和边框（不会延伸到外边距），所以有背景色且边框样式为dashed的情况下是可以将边框颜色指定为白色的。

```css
border-color: white;
```


## border-top 上边框

参考：border。


## border-top-width 上边框宽度

参考：border-width。


## border-top-style 上边框样式

参考：border-style。


## border-top-color 上边框颜色

参考：border-color。


## border-right 右边框

参考：border。


## border-right-width 右边框宽度

参考：border-width。


## border-right-style 右边框样式

参考：border-style。


## border-right-color 右边框颜色

参考：border-color。


## border-bottom 下边框

参考：border。


## border-bottom-width 下边框宽度

参考：border-width。


## border-bottom-style 下边框样式

参考：border-style。


## border-bottom-color 下边框颜色

参考：border-color。


## border-left 左边框

参考：border。


## border-left-width 左边框宽度

参考：border-width。


## border-left-style 左边框样式

参考：border-style。


## border-left-color 左边框颜色

参考：border-color。


## border-radius 边框圆角

属性值表示圆角半径。单位可以使用px或者em，使用em表示相对于元素的字体大小而言。

###  

```css
border-radius: 15px;
border-radius: 1.5em;
```


## border-top-left-radius 左上角边框圆角

参考：border-radius。


## border-top-right-radius 右上角边框圆角

参考：border-radius。


## border-bottom-left-radius 左下角边框圆角

参考：border-radius。


## border-bottom-right-radius 右下角边框圆角

参考：border-radius。


## border-collapse 表格单元格边框折叠/合并

使得相邻的两个单元格共用一个边框，边框宽度为单个边框的宽度。

取值：
- collapse 折叠
- separate 分离（默认值）

###  

```css
table {
  border-collapse: collapse;
}
```


## border-spacing 表格单元格边框间距

边框间距相当于单元格的外边距。表格中的单元格不使用外边距，但可以使用边框和内边距。

###  

示例：去除表格单元格之间的间距，使得两个单元格共用一条边框（宽度为单个边框宽度的两倍）

```css
table {
  border-spacing: 0px;
}
```

示例：水平方向和垂直方向分别设置边框间距(10px为水平间距，30px为垂直间距）

```css
table {
  border-spacing: 10px 30px;
}
```


## caption-side 表格标题位置

取值：
- top（默认值）
- bottom

###  

```css
table {
  caption-side: bottom;
}
```


## color 前景色

该属性控制元素的前景色，包含文本颜色和边框颜色。如果需要单独设置边框颜色的话，可以使用border-color属性。

###  

示例：

```css
h1 {
  color: red;    
}
```

示例：制定颜色的几种方式

```css
h1 {
  color: silver;    
  color: rgb(80%, 40%, 0%);
  color: rgb(204, 102, 0);
  color: #cc6600;
}
```


## display 显示(元素的框类型）

取值：
- table 表格
- table-row 表格中的行
- table-cell 表格中的单元格

###  

示例：表格显示布局（两栏）

```css
#tableContainer {
  display: table;
  border-spacing: 10px;
}
#tableRow {
  display: table-row;
}
#main {
  display: table-cell;
  vertical-align: top;
}
#sidebar {
  display: table-cell;
  vertical-align: top;
}
```


## float 浮动

说明：浮动元素会脱离文档流，对于其后的块元素，会在其下方布局，但是块元素中的内联元素会围绕该浮动元素。

###  

示例：浮动一般配合width属性使用

```css
#amazing {
  width: 200px;
  float: right;
}
```


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


## font 字体

简写形式：

```css
font: font-style font-variant font-weight font-size/line-height font-family
```

其中：
1. font-style、font-variant、font-weight以及line-height都是可选的；
2. line-height的写法和其他属性不一样；
3. font-family各字体之间要使用逗号分隔；

###   

```css
font: small/1.6em Verdana, Helvetica, Arial, sans-serif
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
- Helvetica


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

示例：使用serif字体系列

```css
body {
  font-family: Georgia, "Times New Roman", Times, serif;
}
```

示例：使用monospace字体系列，字体名称中包含括号

```css
body {
  font-family: "Courier New", Courier, monospace;
}
```


## font-size 字体大小

######  

设置字体大小的几种方式：

|方式            	|含义           |备注               		|
|-------------------|---------------|---------------------------|
|px                 |像素           |示例：12px                 |
|%                  |基于父元素的百分比|示例：120%              |
|em                 |基于父元素的百分比|示例：1.2em             |
|关键字             |如：small、medium等|small一般为12px        |

#### 关键字取值

- xx-small
- x-small
- small
- medium
- large
- x-large
- xx-large


#### 默认大小

默认字体大小为16px，h1为200%，h2为150%，h3为120%，h4为100%，h5和h6更小一些。


###  

示例：推荐使用方式

```css
body { font-size: small; }
h1 { font-size: 150% }
h2 { font-size: 120% }
```


## font-style 字体样式

属性取值：normal、italic和oblique。italic表示使用斜体字体，oblique表示使用倾斜文字。

###  

```css
h1 {
  font-style: italic;
}
```


## font-weight 字体粗细

属性取值：normal和bold。其他取值（如：ligther和bolder，以及100的整数倍）都不要使用。

###  

```css
h1 {
  font-weight: normal;
}
```


## font-variant 小型大写字母

取值：
- normal
- small-caps

###  

```css
font-variant: small-caps;
```


## @media 媒体查询

端类型：
- screen 有屏设备
- print 打印设备

其他属性：
- max-width 浏览器最大宽度
- min-width 浏览器最小宽度
- max-device-width 设备最大宽度
- min-device-width 设备最小宽度
- orientation 显示方向，取值：landscape（横向）、portrait（纵向）

###  

```css
@media screen and (min-device-width: 481px) {
  #guarantee {
    margin-right: 250px;
  }    
}
@media print {
  body {
    font-family: Times, "Times New Roman", serif;
  }
}
```


## padding 内边距

如果同时指定了padding-top、padding-right、padding-bottom、padding-left属性，则效果不会叠加，后面的属性值会覆盖前面的。

###  

```css
padding: 25px;
```


## padding-top 上内边距

###  

```css
padding-top: 80px;
```


## padding-right 右内边距

###  

```css
padding-right: 80px;
```


## padding-bottom 下内边距

###  

```css
padding-bottom: 80px;
```


## padding-left 左内边距

###  

```css
padding-left: 80px;
```


## position 定位

取值：
- static  静态定位，即浏览器默认使用的定位方式
- absolute  绝对定位，基于页面进行定位。与浮动float相比，区别在于其后的内联元素不会围绕在其周围
- fixed  固定定位，基于浏览器窗口进行定位
- relative  相对定位，基于原来位置进行定位

定位属性通常与top、right、bottom、left属性共同使用。

###  

示例：绝对定位

```css
#sidebar {
  width: 280px;
  position: absolute;
  top: 100px;
  right: 200px;
}
```


## top 定位元素上边偏移量

###  

```css
#sidebar {
  width: 280px;
  position: absolute;
  top: 100px;
}
```


## right 定位元素右边偏移量

###  

```css
#sidebar {
  width: 280px;
  position: absolute;
  right: 100px;
}
```


## bottom 定位元素下边偏移量

###  

```css
#sidebar {
  width: 280px;
  position: absolute;
  bottom: 100px;
}
```


## left 定位元素左边偏移量

###  

```css
#sidebar {
  width: 280px;
  position: absolute;
  left: 100px;
}
```


## text-decoration 文本装饰

属性取值：none, line-throuth, underline, overline。

###   

示例：删除线

```css
em {
  text-decoration: line-throuth;
}
```

示例：同时增加下划线和上划线
```css
em {
  text-decoration: underline overline;
}
```







示例：使用monospace字体系列，字体名称中包含括号

```css
body {
  font-family: "Courier New", Courier, monospace;
}
```


## line-height 行高/行间距

单位可以是：数字、px, em, %, normal。

###  

示例：

```css
body {
  line-height: 1.6em;
}
```

示例：单位是数字表示各个元素的行高是其自身大小的倍数，而不是统一的大小

```css
body {
  line-height: 1.6;
}
```

示例：设置合理的行间距

```css
body {
  line-height: normal;
}
```


## margin 外边距

###  

示例：分别指定上、右、下、左四个外边距

```css
margin: 0px 20px 30px 10px;
```

示例：分别指定上下、左右外边距

```css
margin: 0px 25px;
```

示例：同时指定上右下左外边距

```css
margin: 25px;
```


## padding 内边距

###  

示例：分别指定上、右、下、左四个内边距

```css
padding: 0px 20px 30px 10px;
```

示例：分别指定上下、左右内边距

```css
padding: 0px 25px;
```

示例：同时指定上右下左内边距

```css
padding: 25px;
```


## text-align 文本对齐（块元素属性）

取值：
- justify
- left
- center
- right

###  

```css
h1 {
  text-align: left;
}
```


## text-decoration 文本装饰

属性取值：none, line-throuth, underline, overline。

###   

示例：删除线

```css
em {
  text-decoration: line-throuth;
}
```

示例：同时增加下划线和上划线
```css
em {
  text-decoration: underline overline;
}
```


## width 内容区宽度

###   

```css
#id {
  width: 20px;
}
```






