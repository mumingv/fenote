# 基本语法

## 注释

支持C、C++两种风格的注释。

```
/* ... */
```

```
// ...
```


## 类型

JS支持7钟数据类型：
- 字符串（String）
- 数字(Number)
- 布尔(Boolean)
- 数组(Array)
- 对象(Object)
- 空（Null）
- 未定义（Undefined）

其中，字符串、数字、布尔为基本数据类型。

### 数字

对于除法运算，如：9/5，得到的值为1.8，而不是1；


## 变量

使用var申明变量，示例：

```javascript
var scoops = 3;
```

- 变量名称由字母、数字、下划线、<font color="red">美元符号</font>组成，不能以数字开头；
- 如果申明变量是未指定值，则默认值为undefined（既是类型也是值）；


## 函数

```javascript
function displayDate() {
    document.getElementById("demo").innerHTML=Date();
}
```


## 字符串

字符串连接使用加号，示例：

```javascript
var message = "Hello " + "henry" + "!";
```


## 分支语句

######  

```javascript
if (a == b) {
    // ...    
} else if (a < b) {
    // ...
} else {
    // ...
}
```


## 循环语句


## 关键字


## 其他


## 说明

1. JS是区分大小写的，比如：myvariable和MyVariable是两个不同的变量；

