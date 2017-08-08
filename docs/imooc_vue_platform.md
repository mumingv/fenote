# 实战：数字产品电商平台

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

### vue的三个特点

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


### vue的实例对象

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


### Vue的组件

#### 简单实例

```javascript
// 引入库'vue'，import关键字是ES6的语法，类似于之前的require关键字
import Vue from 'vue'

// 实例化一个Vue对象，将Vue组件加入到页面上，这里的'new Vue'是一个根组件
new Vue({
	el: '#app',
	template: "<p>hello world {{ word }}</p>",  // 原index.html页面中的div元素会被模版里的p元素替换
	data: {
		word: 'hello world2'  // 数据渲染，这里的word对应模版中的{{ word }}
	}
})
```


#### 组件注册和引入

##### 全局组件

```javascript
//main.js
// 注册全局组件
Vue.component('my-header', {
	template: '<p>this is my header</p>'
})
```

```html
// index.html
<div id="app">
    <my-header></my-header>
    hello
</div>
```


##### 局部组件

<font color="red">
注意：组件里的data不能使用引用赋值，而必须使用函数返回对象的形式赋值。
</font>


```javascript
// 引入库'vue'，import关键字是ES6的语法，类似于之前的require关键字
import Vue from 'vue'

// 子子组件对象
var myHeaderChild = {
	template: '<p>i am my header child. {{ name }} </p>',
	data: function() {
		return {
			name: 'Henry'
		}
	}
}

// 子组件对象
var myHeader =  {
	template: '<p><my-header-child></my-header-child>this is my header</p>',
	components: {
		'my-header-child': myHeaderChild
	}
}

// 实例化一个Vue对象，将Vue组件加入到页面上，这里的'new Vue'是一个根组件
new Vue({
	el: '#app',
	data: {
		word: 'hello world2'  // 数据渲染，这里的word对应模版中的{{ word }}
	},
	// 子组件（非全局组件）
	components: {
		'my-header': myHeader
	}
})
```

```html
// index.html
<div id="app">
    <my-header></my-header>
    hello
</div>
```


### vue的相关概念

- 全局api
- 实例选项
- 实例属性／方法
- 指令
- 内置组件


## 功能接口（1）

基础代码：

```html
// index.html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>vuedemo2</title>
  </head>
  <body>
    <div id="app">
    </div>
    <!-- built files will be auto injected -->
  </body>
</html>
```

```javascript
// main.js
import Vue from 'vue'
import App from './App'

new Vue({
	el: '#app',
	// vue2.0需要使用render方法渲染外部引入的App组件，这个是ES6的写法（函数只有一个参数时可以这样简写）
	// render: h => h(App)
	// 等价于：
	render: function(h) {
		return h(App)
	}
})
```

```javascript
// App.vue
<template>
  <div>
    {{ hello }}
    <p v-text="hello"></p>
    <p v-html="hello"></p>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      hello: '<span>world</span>'
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body{
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}
</style>
```


### 文本渲染 v-html v-text {{}}

#### 区别

`v-text`和`{{}}`一样，仅仅是字符串的简单替换。而`v-html`会解析字符串中的html标签。


#### {{}}中表达式的写法

```javascript
// App.vue
<template>
  <div>
    <p>{{ num + 1 }}</p>
    <p>{{ status ? 'success' : 'fail'}}</p>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      num: 1,
      status: true
    }
  }
}
</script>
```


### 列表渲染 v-for 数组、对象、子组件

#### 数组

```javascript
// App.vue
<template>
  <div>
    <ul>
      <li v-for="(item, index) in list" :class="{odd:index % 2}">{{ item.name }} - {{ item.price }} - {{ index }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      list: [
        {
          name: 'apple',
          price: 34
        },
        {
          name: 'banana',
          price: 56
        },
        {
          name: 'pear',
          price: 37
        }
      ]
    }
  }
}
</script>

<style>
.odd {
  display: none;
}
</style>
```


#### 对象

```javascript
// App.vue
<template>
  <div>
    <ul>
      <li v-for="(value, key) in objList">{{ key + " " + value }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      objList: {
        name: 'apple',
        price: 34,
        color: 'red',
        weight: 14
      }
    }
  }
}
</script>
```


#### 子组件

```javascript
// App.vue
<template>
  <div>
    {{ hello }}
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      hello: 'i am component a'
    }
  }
}
</script>

<style scoped>

</style>
```

```javascript
// App.vue
<template>
  <div>
    <component-a v-for="(value, key) in objList" key="key "></component-a>
  </div>
</template>

<script>
import componentA from './components/a'
export default {
  components: {componentA},
  data: function() {
    return {
      objList: {
        name: 'apple',
        price: 34,
        color: 'red',
        weight: 14
      }
    }
  }
}
</script>
```

<font color="red">
说明：也可以写成下面的形式。
</font>

```
<componentA v-for="(value, key) in objList" key="key "></componentA>
```

``` 
components: {
    componentA: componentA
},
```


### 列表数据的同步更新方法（双向绑定）

方法1: 使用数组的push方法增加一项

```javascript
// App.vue
<template>
  <div>
    <ul>
      <li v-for="(item, index) in list">{{ item.name }} - {{ item.price }}</li>
    </ul>
    <button v-on:click="addItem"></button>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      list: [
        {
          name: 'apple',
          price: 34
        },
        {
          name: 'banana',
          price: 56
        },
        {
          name: 'pear',
          price: 37
        }
      ]
    }
  },
  methods: {
    addItem() {
      this.list.push({
        name: 'pineapple',
        price: 256
      })
      console.log(this.list)
    }
  }
}
</script>
```

方法2: 使用全局API设置数组的某一项

```
<script>
import Vue from 'vue'
export default {
  data: function() {
    return {
      list: [
        {
          name: 'apple',
          price: 34
        },
        {
          name: 'banana',
          price: 56
        },
        {
          name: 'pear',
          price: 37
        }
      ]
    }
  },
  methods: {
    addItem() {
      Vue.set(this.list, 1, {
        name: 'pineapple',
        price: 256
      })
      console.log(this.list)
    }
  }
}
</script>
```


### Vue标签属性和条件渲染

#### 一般属性绑定

标签属性的绑定使用v-bind指令，该绑定是一种动态绑定，即：当属性值变量在其他地方被修改以后，该属性值也会动态地改变。

```html
<a v-bind:href="link" v-bind:title="hello">to baidu</a>
```

可以通过v-bind将变量值带入到组件当中去使用。

```
<componentA v-bind:dataA="dataA"></componentA>
```


#### class绑定

通过v-bind绑定的class和原生的class属性是不冲突的。

```html
<template>
  <a class="link-ref" v-bind:class="classStr">to baidu</a>
</template>
```

```javascript
<script>
export default {
  data: function() {
    return {
      classStr: 'red-font'
    }
  }
}
</script>
```

通过v-bind绑定的class可以使用对象。

```html
<template>
  <a class="link-ref" v-bind:class="classStr">to baidu</a>
</template>
```

```javascript
<script>
export default {
  data: function() {
    return {
      className: {
        'red-font': false,
        'blue-font': true
      }
    }
  }
}
</script>
```


#### style绑定

```html
<template>
  <a class="link-ref" v-bind:style="linkCss">to baidu</a>
</template>
```

```javascript
<script>
export default {
  data: function() {
    return {
      linkCss: {
        'color': 'red',
        'font-size': '20px'
      }
    }
  }
}
</script>
```


#### 条件渲染 v-if v-show v-else

v-if和v-show的区别：v-if通过增删DOM元素的方式控制是否显示，v-show通过设置display属性的方式控制是否显示。

```html
<template>
  <a v-if="isPartA">partA</a>
  <a v-show="!isPartA">partB</a>
  <button v-on:click="toggle">toggle</button>
</template>
```

```javascript
<script>
export default {
  data: function() {
    return {
      isPartA: true
    }
  },
  methods: {
    addItem() {
      Vue.set(this.list, 1, {
        name: 'pineapple',
        price: 256
      })
      console.log(this.list)
    },
    toggle() {
      this.isPartA = !this.isPartA
    }
  }
}
</script>
```

v-else使用示例：

```html
<a v-if="isPartA">partA</a>
<a v-else>no-data</a>
```


### 事件绑定 - 内置事件绑定 v-on

#### 基本写法

v-on是指令，click是参数，stop是修改器。

```html
<button v-on:click="toggle">toggle</button>
```

#### 缩写形式

v-on指令可以缩写成如下形式：

```html
<button @click="toggle">toggle</button>
```

#### 使用修改器

下面的修改器.stop表示“阻止冒泡事件“。

```html
<button v-on:click.stop="toggle">toggle</button>
```

下面的修改器.enter表示按下回车键时执行执行对应的处理函数。

方式1: 使用键别名

```html
<input @keydown.enter="onKeydown">
```

方式2: 使用键代码

```html
<input @keydown.13="onKeydown">
```


### 事件绑定 - 自定义事件绑定

针对子组件向外触发的自定义事件，步骤如下：

#### 引入子组件

```
// App.vue
<template>
  <div>
    <ul>
    <comA></comA>
  </div>
</template>

<script>
import Vue from 'vue'
import comA from './components/a'
export default {
  components: {
    comA
  }
}
</script>
```


#### 根组件增加自定义事件处理函数

其中的my-event为自定义事件名称；onComAMyEvent是事件处理函数，其参数paramFromA由子组件使用emit触发事件时带过来的。

```
// App.vue
<template>
  <div>
    <ul>
    <comA @my-event="onComAMyEvent"></comA>
  </div>
</template>

<script>
import Vue from 'vue'
import comA from './components/a'
export default {
  components: {
    comA
  },
  methods: {
    onComAMyEvent(paramFromA) {
      console.log("onComAMyEvent " + paramFromA)
    }
  }
}
</script>
```


#### 子组件触发事件

子组件新增一个按钮用于触发自定义事件。

```
// a.vue
<template>
  <div>
    {{ hello }}
    <button @click="emitMyEvent">emit</button>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      hello: 'i am component a'
    }
  },
  methods: {
    emitMyEvent() {
      this.$emit('my-event', this.hello)
    }
  }
}
</script>
```


### 事件绑定 - 表单事件绑定 v-model

v-model指令有lazy、number和trim这三个修饰符。

```html
<template>
  <div>
    <input type="text" name="" v-model.lazy="myVal">
    {{ myVal }}
  </div>
</template>

<script>
import Vue from 'vue'

export default {
  data: function() {
    return {
      myVal: ''
    }
  }
}
</script>
```



















