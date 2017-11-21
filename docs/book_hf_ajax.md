# HF-Ajax

### 代码路径

GitHub（源码）: [fe/books/Head-First-Ajax/origin](https://github.com/mumingv/fe/tree/master/books/Head-First-Ajax/origin)

GitHub（我的代码）: [fe/books/Head-First-Ajax/origin](https://github.com/mumingv/fe/tree/master/books/Head-First-Ajax/mine)

### 环境部署

每个章节目录下有一个部署脚本`deploy.sh`，执行部署脚本后会自动在浏览器中打开页面。

示例：

```
$ cd ~/Sites/fe/books/Head-First-Ajax/mine/ch01
$ sh deploy.sh
```

### 学习笔记

## 使用Ajax

### 

对于`<div>`元素样式的设置，可以遵循以下顺序：宽width、高height / 边框border、内外边距padding、margin / 定位position、背景background ／ 文本对齐text-align。


### 

样式通过`<link>`的href属性引入，脚本通过`<script>`的src属性引入。


### 源码分析（一）

###### 

```javascript
window.onload = initPage;

function initPage() {
  // find the thumbnails on the page
  thumbs = document.getElementById("thumbnailPane").getElementsByTagName("img");

  // set the handler for each image
  for (var i = 0; i < thumbs.length; i++) {
    image = thumbs[i];
    
    // create the onclick function
    image.onclick = function() {
      // find the image name
      detailURL = 'images/' + this.title + '-detail.jpg';
      document.getElementById("itemDetail").src = detailURL;
      getDetails(this.title);
    }
  }
}
```

`window.onload = initPage;`用于指定窗口加载事件触发时调用的函数，参考：[链接](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onload)。

元素对象的`length`属性表示元素节点的个数，参考：[runoob](http://www.runoob.com/jsref/prop-nodelist-length.html)。

`image.onclick = function() {...}`给其中的元素对象`<img>`绑定点击事件，`onclick`是[HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)的一个属性，绑定的事件处理函数是一个匿名函数。

JS的字符串使用加号（`+`）连接。

`<img>`对应的HTML DOM为[HTMLImageElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement)。

<font color="red">
事件回调函数中引用对象的话，必须使用this，而不能使用对象变量，如：不能使用这里的image代替this。
</font>

### 源码分析（二）

###### 

```javascript
function createRequest() {
  try {
    request = new XMLHttpRequest();
  } catch (tryMS) {
    try {
      request = new ActiveXObject("Msxml2.XMLHTTP");
    } catch (otherMS) {
      try {
        request = new ActiveXObject("Microsoft.XMLHTTP");
      } catch (failed) {
        request = null;
      }
    }
  }
  return request;
}

function getDetails(itemName) {
  console.log("title's value: " + itemName);
  request = createRequest();
  if (request == null) {
    alert("Unable to create request");
    return;
  }
  var url= "getDetails.php?ImageID=" + escape(itemName);
  request.open("GET", url, true);
  request.onreadystatechange = displayDetails;
  request.send(null);
}

function displayDetails() {
  if (request.readyState == 4) {
    if (request.status == 200) {
      detailDiv = document.getElementById("description");
      detailDiv.innerHTML = request.responseText;
    }
  }
}
```

对于`try...catch...`，catch后括号中表示异常的字符串可以随便写。

`new XMLHttpRequest()`用于构造与后台交互的对象，参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)。

`new ActiveXObject("Microsoft.XMLHTTP")`为IE6及之前版本创建交互对象的方法，参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest_in_IE6)。

`Msxml2`和`Microsoft`是IE早期版本使用的库名，XMLHTTP可能存在于其中的某一个库。

`alert()`是window对象的一个方法，用于弹出一个对话框，参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/alert)。

`escape()`是JS提供的全局函数，用于对字符串进行编码，参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference)。

`XMLHttpRequest.open()`用于初始化一个请求，而不是发送请求，发送请求使用`XMLHttpRequest.send()`函数。`open()`的第三个参数为true表示异步执行。参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/open)。

`XMLHttpRequest.onreadystatechange`事件属性用于当readyState属性值变化时触发回调函数。参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/onreadystatechange)。

`XMLHttpRequest.readyState`属性表示XMLHttpRequest客户端当前所处的状态，取值：0-4，其中4表示请求完成。参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/readyState)。

`XMLHttpRequest.status`属性表示服务端应答的状态码，取值和[HTTP状态码](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)一致，其中200表示成功。参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/status)。

`XMLHttpRequest.send()`用于初始化发送一个GET或者POST请求。参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/send)。

`XMLHttpRequest.onreadystatechange`事件属性可以用`XMLHttpRequest.onload`事件属性替代。

`XMLHttpRequest.responseText`属性表示服务端应答的数据；而`XMLHttpRequest.response`返回的数据除了text类型之外，还可以是其他的类型，如：JS对象。参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseText)。

`element.innerHTML`表示元素的html内容，参考：[MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/innerHTML)。


## 设计Ajax应用

### 

几种常用的控件有：`<input>`是用户输入控件；`<select>`是用户选择控件；`<textarea>`是多行文本编辑控件。

`<label>`元素表示用户界面中x项目的标题，通常与控件配合使用。

### 源码分析

###### 

```javascript
function showUsernameStatus() {
  if (request.readyState == 4) {
    if (request.status == 200) {
      if (request.responseText == "okay") {
        document.getElementById("username").className = "approved";
        document.getElementById("register").disabled = false;
      } else {
        document.getElementById("username").className = "denied";
        document.getElementById("username").focus();
        document.getElementById("username").select();
        document.getElementById("register").disabled = true;
      }
    }
  }
}
```

HTMLInputElement的focus()方法用于定位到控件内容，默认继续输入内容时原有内容不会被覆盖；select()方法也用于定位到控件内容，默认继续输入内容时原有内容会被覆盖。参考：[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLInputElement)。

```css
#username {
  background: #fff url("../images/status.gif") 202px 0px no-repeat;
  padding: 0 20px 0 2px; 
  width: 198px;
}
#username.thinking {
  background-position: 202px -19px;
}
#username.approved {
  background-position: 202px -35px;
}
#username.denied {
  background-color: #FF8282;
  background-position: 202px -52px;
}
```

background-color是从元素的边框左上角起到边框右下角止；background-image却不一样，在no-repeat的情况下，它是从padding边缘的左上角起而到border的右下角边缘止。


## JavaScript事件

### 源码分析

###### 

```css
#navigation a {
  display: block;
  width: 155px;
  border: 0px red solid;
  padding: 140px 0 0 0;
  margin: 0 0 10px 0;
  height: 0;
  overflow: hidden;
}

#navigation a#beginners {
  background: url("../images/beginnersBtn.png") no-repeat;
}
#navigation a#intermediate {
  background: url("../images/intermediateBtn.png") no-repeat;
}
#navigation a#advanced {
  background: url("../images/advancedBtn.png") no-repeat;
}
```

这里图片显示的总体思想是：在padding区域显示背景图片，将内容区的高度设置为0并配合`overflow: hidden;`以不显示a标签的内容。

`width`和`height`是指内容区的宽度和高度，内容区是指padding里面的区域，不包含padding。

影藏a标签内容时必须使用`height: 0;`和`overflow: hidden;`两条CSS语句才行。如果只使用`height: 0;`，虽然内容区不占用空间，但是其中的内容仍旧会显示。如果只使用`overflow: hidden;`将不会有任何效果，因为overflow属性必须基于内容区固定的场景，即必须指定width和height属性时overflow属性才会生效，


```javascript
function initPage() {
  var tabs = 
    document.getElementById("tabs").getElementsByTagName("a");
  for (var i=0; i<tabs.length; i++) {
    var currentTab = tabs[i];
    currentTab.onmouseover = showHint;
    currentTab.onmouseout = hideHint;
    currentTab.onclick = showTab;
  }

  var buttons = 
    document.getElementById("navigation").getElementsByTagName("a");
  for (var i=0; i<buttons.length; i++) {
    var currentBtn = buttons[i];
    currentBtn.onmouseover = showHint;
    currentBtn.onmouseout = hideHint;
    currentBtn.onclick = showTab;
    currentBtn.onmouseover = buttonOver;
    currentBtn.onmouseout = buttonOut;
  }
}
```

`onmouseover`和`onmouseout`属性用来设置当前元素的`mouseove事件`和`mouseout事件`的事件处理函数。鼠标相关的事件还有`onmouseup`、`onmousedown`和`onmousemove`。参考：[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onmouseover)。


## 多个事件处理程序

### 源码分析

```javascript
function getActivatedObject(e) {
  var obj;
  if (!e) {
    // early version of IE
    obj = window.event.srcElement;
  } else if (e.srcElement) {
    // IE 7 or later
    obj = e.srcElement;
  } else {
    // DOM Level 2 browser
    obj = e.target;
  }
  return obj;
}
```

标准的事件模型：都是通过`e.target`获取事件对象。

IE的事件模型与标准不同：当e不是对象时通过`window.event.srcElement`获取事件对象；当e是对象时通过`e.srcElement`获取事件对象。


```javascript
function addEventHandler(obj, eventName, handler) {
  if (document.attachEvent) {
    obj.attachEvent("on" + eventName, handler);
  } else if (document.addEventListener) {
    obj.addEventListener(eventName, handler, false);
  }
}
```

标准的事件模型：通过`EventTarget.addEventListener()`方法增加事件处理函数，事件名称参数<b>不需要</b>增加`on`。参考[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/EventTarget/addEventListener)。

IE的事件模型与标准不同：通过`EventTarget.attachEvent()`方法增加事件处理函数，事件名称参数<b>需要</b>增加`on`。参考[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/EventTarget/attachEvent)。

使用`document.attachEvent`和`document.addEventHandler`来判定函数是否支持。

使用`addEventListener`或`attachEvent`方法可以给同一个对象增加多个事件处理函数，而通过事件属性只能增加一个事件处理函数。


```javascript
addEventHandler(elBtn, "mouseover", buttonOver);

function buttonOver(e) {
  console.log("buttonOver");
  me = getActivatedObject(e);
  me.className = "active";
}
```

事件处理函数默认都会携带一个事件作为参数，可以根据这个事件获取对应的对象。当然也可以直接使用this关键字表示事件对象，但是这种方式在老的IE中不支持。


## 异步应用

### 源码分析

```
#coverBar {
  width: 440px;
  height: 115px;
  position: absolute;
  top: 495px;
  left: 182px;
  overflow: hidden;
}

#coverBar img {
  position: absolute;
  top: 0;
}
```

`position: absolute;`的定位本质上是根据最近的非static祖先元素进行定位的，而不是之前理解的根据页面左上角进行定位。


## DOM

###### 

### 源码分析

```
function cellIsEmpty(cell) {
  var image = cell.firstChild;
  while (image.nodeName == "#text") { image = image.nextSibling; }
  if (image.alt == "empty")
    return true; 
  else 
    return false; 
}
```

`firstChild`是[文档对象模型DOM接口](https://developer.mozilla.org/zh-CN/docs/Web/API/Document_Object_Model)`Node`的一个属性，具体参考：[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Node)。






















