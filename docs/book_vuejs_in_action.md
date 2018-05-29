# Vue.js 实战

作者：梁灏，书籍源码：[GitHub](https://github.com/icarusion/vue-book)

我的代码：[GitHub](https://github.com/mumingv/fe/tree/master/books/my-vue-book)


## 第1章 初识 Vue.js


## 第2章 数据绑定和第一个Vue应用


## 第3章 计算属性

`3.3 计算属性缓存`一节中有个示例没有看懂，代码参考：[GitHub](https://github.com/mumingv/fe/blob/master/books/my-vue-book/ch03-computed-attr/07-computed-attr-cache.html)。

## 第4章 v-bind 及 class 与 style 绑定


## 第5章 内置指令


## 第6章 表单与 v-model


## 第13章 实战：知乎日报项目开发

### 启动方法

启动代理服务

```
$ node proxy.js
接口代理运行在 http://127.0.0.1:8010/
图片代理运行在 http://127.0.0.1:8011/
```

启动webpack服务

```
$ npm run dev
```


### 知乎接口

- 主题列表：http://news-at.zhihu.com/api/4/themes
- 某个主题下的文章列表：http://news-at.zhihu.com/api/4/theme/13
- 每日推荐：http://news-at.zhihu.com/api/4/news/before/20180428
- 单篇文章：http://news-at.zhihu.com/api/4/news/7097426
- 文章评论：http://news-at.zhihu.com/api/4/story/7097426/short-comments


### 开发步骤

**13.1 分析与准备**

###### 
|日期		|事项							|备注					|
|-----------|-------------------------------|-----------------------|
|2018-02-27	|从第10章拷贝项目作为开发基础		|[GitHub](https://github.com/mumingv/fe/commit/2fd07f7959385c4b1ac34f571f826982e1258059)|
|2018-02-27	|使用request实现知乎的接口代理 		|[GitHub](https://github.com/mumingv/fe/commit/05529ee348a8267c40a9820b805bbd6a2d0ad1e9)|
|2018-02-27	|使用axios插件调用ajax请求 		|[GitHub](https://github.com/mumingv/fe/commit/0d35498061393b36f028109bbc93190f625ea19c)|


**13.2 推荐列表与分类**
###### 
|日期		|事项							|备注					|
|-----------|-------------------------------|-----------------------|
|2018-04-27	|13.2.1 搭建基本结构	|[GitHub](https://github.com/mumingv/fe/commit/ed3dfbec4a24810639745dbca735abcf81cf25ae)|
|2018-04-28	|13.2.2 主题日报		|[GitHub](https://github.com/mumingv/fe/commit/4b9257cbfc706d70181576698a179d060e03ded2)|
|2018-05-10	|13.2.3 每日推荐		|[GitHub](https://github.com/mumingv/fe/commit/7e2d4d0aa57620a9aba4e540631efa82494c2e48)|
|2018-05-10	|13.2.4 自动加载更多推荐列表	|[GitHub](https://github.com/mumingv/fe/commit/bb15de306b662dcc34113d968734a3ad037de749)|


**13.3 文章详情页**
###### 
|日期		|事项							|备注					|
|-----------|-------------------------------|-----------------------|
|2018-05-14	|13.3.1 加载内容	|[GitHub](https://github.com/mumingv/fe/commit/b29c557b2d0b3f314687d2b9de774a9251ad3237)|
|2018-05-20	|13.3.2 加载评论	|[GitHub](https://github.com/mumingv/fe/commit/7d085c13a3bcd208f3a2ef9e43263fcf2c3f8e5a)|


## 第14章 实战：电商网站项目开发

### 启动方法

安装插件

```
$ npm install
```

启动webpack服务

```
$ npm run dev
```


### 开发步骤

**14.1 项目工程搭建**

###### 
|日期		|事项							|备注					|
|-----------|-------------------------------|-----------------------|
|2018-05-20	|拷贝第10章 ch10-webpack 的代码	|[GitHub](https://github.com/mumingv/fe/commit/3be4852c5095dd4e61867f845d8f45b8e13f9b81)|
|2018-05-21	|14.1 项目工程搭建		|[GitHub](https://github.com/mumingv/fe/commit/e00812e8d6b5ec4a3740a40d2cf473851874f033)|


**14.2 商品列表页**

###### 
|日期		|事项							|备注					|
|-----------|-------------------------------|-----------------------|
|2018-05-21	|14.2.1 需求分析与模块拆分	|无|
|2018-05-23	|14.2.2 商品简介组件	|[GitHub](https://github.com/mumingv/fe/commit/7754933e10c75239ad2926559ddc4150de3deb2e)|
|	|14.2.3 列表按照价格、销量排序	|[GitHub---](https://github.com/mumingv/fe/commit/)|
|	|14.2.4 列表按照品牌、颜色筛选	|[GitHub---](https://github.com/mumingv/fe/commit/)|


**14.3 商品详情页**

###### 
|日期		|事项							|备注					|
|-----------|-------------------------------|-----------------------|
|	|14.3 商品详情页	|[GitHub---](https://github.com/mumingv/fe/commit/)|


**14.4 购物车**

###### 
|日期		|事项							|备注					|
|-----------|-------------------------------|-----------------------|
|	|14.4.1 准备数据	|[GitHub---](https://github.com/mumingv/fe/commit/)|
|	|14.4.2 显示和操作数据	|[GitHub---](https://github.com/mumingv/fe/commit/)|
|	|14.4.3 使用优惠码	|[GitHub---](https://github.com/mumingv/fe/commit/)|


### 开发笔记

#### 配置less的方法

1.安装less和less-loader插件

```
$ npm install less --save-dev
$ npm install less-loader --save-dev
```

2.在webpack始终配置less-loader

参考：`14.2.2 商品简介组件`一节代码。





