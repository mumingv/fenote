# Vue2实践揭秘

## 例说Vue.js

本章记录了vue-todos项目的开发步骤。

### 安装并运行框架

```
$ vue init webpack-simple vue-todos
$ cd vue-todos/
$ npm install
```

## 工程化的Vue.js开发

略。


## 路由与页面间导航

Sketch是一个矢量图工具，可以用来设计页面。

### vue-router

改变浏览器地址而不向服务器发出请求有两种方法：
1. 在地址中加入#以欺骗浏览器，让浏览器以为是在进行页内导航。
2. 使用HTML5的window.history功能，使用URL的Hash来模拟一个完整的URL。

#### 安装

安装

```
npm install vue-loader --save-dev
```

使用

```
// main.js
import Vue from 'vue'
import VueRouter from 'vue-router'
Vue.use(VueRouter)
```


#### 路由配置

单页式应用没有“页”的概念，我们看到的“页面”是使用vue-router配合配合各个组件形成的。
1. 页面是一个抽象的逻辑概念，用于划分功能场景。
2. 组件是页面在Vue的具体实现方式。


#### 示例

```
const router = new VueRouter({
    mode: 'history',
    base: __dirname,
    linkActiveClass: "active",
    routes: [
        {name:'Home', path: '/', component: Home},
        {name:'Categories',path: '/categories', component: Category},
        {name:'ShoppingCart',path: '/shopping-cart', component: ShoppingCart},
        {name:'Me',path: '/me', component: Me},
        {name:'BookDetail',path: '/books/:id', component: BookDetail}
    ]
})
```

其中：
1. mode表示路由模式；
2. base为应用的基路径；
3. routes数组设置具体的路由规则，使用三个字段：name、path和component。其中，path为页面URL的路径。


### 路由的模式

有三种路由模式，如下：

#### Hash

所有浏览器都支持。URL形如下面的形式：

```
http://localhost/#home
```


#### History

依赖 HTML5 History API 和服务器配置。URL形如下面的形式：

```
http://localhost/home
```


#### Abstract

支持所有JavaScript运行环境。如果发现没有浏览器的API，就会自动强制进入这个模式。


### 路由与导航

路由使用的方式有两种：
1. 显示指定路由；
2. 命名路由。

#### 动态路由

下面示例中的BookDetail使用的就是动态路由，因为定义的路由数量是不确定的。

```
const router = new VueRouter({
    mode: 'history',
    base: __dirname,
    linkActiveClass: "active",
    routes: [
        {name:'Home', path: '/', component: Home},
        {name:'Categories',path: '/categories', component: Category},
        {name:'ShoppingCart',path: '/shopping-cart', component: ShoppingCart},
        {name:'Me',path: '/me', component: Me},
        {name:'BookDetail',path: '/books/:id', component: BookDetail}
    ]
})
```


### History的控制

使用$router的三个方法进行控制：push()、append()、replace()。


### 关于Fallback

对于Nginx，使用如下配置：

```
location / {
	try_files $uri $uri/ /index.html;
}
```















