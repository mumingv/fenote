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
|2018-04-27	|13.2.3 每日推荐		|[GitHub](https://github.com/mumingv/fe/commit/7e2d4d0aa57620a9aba4e540631efa82494c2e48)|
|2018-04-27	|13.2.4 自动加载更多推荐列表	|[GitHub](https://github.com/mumingv/fe/commit/bb15de306b662dcc34113d968734a3ad037de749)|


















