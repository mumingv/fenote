# 数字产品电商平台

## 课程信息

课程地址：http://coding.imooc.com/class/91.html

代码：fe/video/imooc/vue/vue_platform


## 参考资料

vue.js中文官网：https://cn.vuejs.org/

vue.js源码：https://github.com/vuejs/vue

vue.js官方工具：https://github.com/vuejs

vue.js官方论坛：https://forum.vuejs.org


## 课程简介

Vue.js是轻量级的前端界面框架。Vue.js在2016年10月发布了	2.0版本。

Vue.js的几个特点：

- 数据渲染／数据同步
- 组件化／模块化
- 其他功能：路由、vue-resource（ajax）、数据流


## Vue.js简介

### vue三个特点

#### 响应式 - 双向绑定

双向绑定的样例代码：

```html
<div id="app">
	<p>{{ message }}</p>
	<input v-model="message">
</div>
```

```javascript
new Vue({
	el: '#app',
	data: {
		message: 'Hello vue.js!'
	}
})
```


#### 组件化 - 模块化

打包工具：
- Webpack + vue-loader
- Browserify + vueify

#### 单文件组件

单文件组件：html、css、js放在同一个文件内。

下面scoped属性的作用是将样式限定在当前的文件中，以避免污染其他的组件。

```css
<style scoped>
	color: #42b983;
</style>
```

预加载器，如：jade、less。即：定义模版或样式使用的语言。

```html
<template lang="jade">
	...
</template>
```

```css
<style lang="less">
	...
</style>
```


### vue实例对象

vue实例对象即为通过Vue类进行实例化的对象。如下所示：

```javascript
var my = new Vue({
	el: '#app',
	template: '<div><other-component></div>'
	data: {
		fruit: 'apple',
		message: 'Hello vue.js!'
	}
})
```

`Vue`是构造函数，`el`、`template'和`data`是参数选项。

#### el

`el`表示这个vue对象所装载的位置。

如果要装载到`<body>`元素，可以写成：

```
el: 'body'
```

如果要装载到id为`app`的元素，可以写成：

```
el: '#app'
```


#### template

`template`就是html代码，或者是包含指令和其他组件的一个html片段。

```
template: '<div>{{ fruit }}</div>'
```

```
template: '<div><other-component></div>'
```


#### data

`data`里的数据会被代理到生成的示例对象中，当需要使用'apple'这个值的时候，就可以用`my.fruit`来获取。


#### components

下面是将根组件挂载到`body`元素上。

```
new Vue({
	el: 'body',
	components: { App }
})
```

根组件可以包含子组件，从而形成一个组件树以方便管理。


#### vue示例对象的生命周期

参考：https://cn.vuejs.org/v2/guide/instance#实例生命周期


## 环境搭建和常用插件



















