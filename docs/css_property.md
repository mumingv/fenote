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

可以同时指定边框的宽度、样式、颜色。

###  

```
border: 1px solid red;
```


## border-width 边框宽度

###  

```css
border-width: 1px;
```


## border-style 边框样式

常用取值：

- solid 实线
- dashed 点线
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


## line-height 行高/行间距

单位可以是：px, em, %。

###  

示例：

```css
body {
  line-height: 1.6em;
}
```


## margin 外边距

###  

示例：

```css
margin: 25px;
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


## line-height 行高/行间距

单位可以是：px, em, %。

###  

示例：

```css
body {
  line-height: 1.6em;
}
```


## margin 外边距

###  

示例：

```css
margin: 25px;
```


## padding 内边距

###  

示例：

```css
padding: 25px;
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







