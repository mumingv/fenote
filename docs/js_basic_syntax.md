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

ES6新增对Map和Set类型的支持。


### 数字（Number）

对于除法运算，如：9/5，得到的值为1.8，而不是1；


### 布尔（Boolean）

JavaScript把null、undefined、0、NaN和空字符串''视为false，其他值一概视为true。


## 变量

使用var申明变量，示例：

```javascript
var scoops = 3;
```

- 变量名称由字母、数字、下划线、<font color="red">美元符号</font>组成，不能以数字开头；
- 如果申明变量是未指定值，则默认值为undefined（既是类型也是值）；


## 函数

### 函数定义

#### 示例：使用普通方式定义函数

```javascript
function abs(x) {
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
}
```


#### 示例：使用匿名方式定义函数

```javascript
var abs = function (x) {
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
};
```


### 说明

- 调用函数时，如果参数是基本类型（数字、字符串、布尔值），则为值传递；如果参数是数组或对象，则为引用传递；
- 如果函数没有使用return指明返回值，则默认返回undefined。


## 字符串

字符串连接使用加号，示例：

```javascript
var message = "Hello " + "henry" + "!";
```


## 分支语句 if

### if 

#### 示例

```javascript
if (age >= 6) {
    alert('teenager');
} else if (age >= 18) {
    alert('adult');
} else {
    alert('kid');
}

```


## 循环语句 for for...in while do...while

### for

#### 示例

```javascript
for (i=1; i<=10000; i++) {
    x = x + i;
}
```


### for...in

#### 示例：遍历对象

```javascript
var o = {
    name: 'Jack',
    age: 20,
    city: 'Beijing'
};
for (var key in o) {
    alert(key); // 'name', 'age', 'city'
}
```


#### 示例：遍历数组

```javascript
var a = ['A', 'B', 'C'];
for (var i in a) {
    alert(i); // '0', '1', '2'
    alert(a[i]); // 'A', 'B', 'C'
}
```


### while

#### 示例

```javascript
var x = 0;
var n = 99;
while (n > 0) {
    x = x + n;
    n = n - 2;
}
```


### do...while

#### 示例

```javascript
var n = 0;
do {
    n = n + 1;
} while (n < 100);
```


## 关键字

### ...（ES6）

`...`表示rest参数。

#### 示例

```javascript
function foo(a, b, ...rest) {
    console.log('a = ' + a);
    console.log('b = ' + b);
    console.log(rest);
}

foo(1, 2, 3, 4, 5);
// 结果:
// a = 1
// b = 2
// Array [ 3, 4, 5 ]

foo(1);
// 结果:
// a = 1
// b = undefined
// Array []
```


### arguments

arguments仅仅在函数内部使用，其保存了用户传入的所有参数。

#### 示例

```javascript
function foo(x) {
    alert(x); // 10
    for (var i=0; i<arguments.length; i++) {
        alert(arguments[i]); // 10, 20, 30
    }
}
foo(10, 20, 30);
```


### const（ES6）

const用于定义常量，其作用域和let一样，都是块级作用域。

#### 示例

```javascript
const PI = 3.14;
PI = 3; // 某些浏览器不报错，但是无效果！
PI; // 3.14
```


### delete

#### 示例：删除对象的属性

```javascript
delete fido.age;
```


### in

#### 示例：检测某个属性是否在指定的对象中

```javascript
var xiaoming = {
    name: '小明',
    birth: 1990,
    school: 'No.1 Middle School',
    height: 1.70,
    weight: 65,
    score: null
};
'name' in xiaoming; // true
'grade' in xiaoming; // false
```


### let

let用于定义变量，与var的区别在于两者的作用域不同。let定义的变量是块级作用域；而var定义的变量是函数作用域。

#### 示例

```javascript
'use strict';
function foo() {
    var sum = 0;
    for (let i=0; i<100; i++) {
        sum += i;
    }
    i += 1; // SyntaxError
}
```


### typeof

typeof用于检查变量的类型。

#### 示例：入参检查

```javascript
function abs(x) {
    if (typeof x !== 'number') {
        throw 'Not a number';
    }
    if (x >= 0) {
        return x;
    } else {
        return -x;
    }
}
```


#### 


## 其他


## 说明

1. JS是区分大小写的，比如：myvariable和MyVariable是两个不同的变量；

