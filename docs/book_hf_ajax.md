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




