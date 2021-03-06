# 《vue.js入门基础》

## 环境安装

### 安装node版本管理工具

参考：https://github.com/alsotang/node-lessons/tree/master/lesson0

```
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.25.2/install.sh | bash
```

能执行nvm命令说明安装成功。

```
$ nvm
```


### 安装node

查看可用的版本

```
$ nvm ls-remote
```

所有的node版本可以参考官方文档：https://github.com/nodejs/node/blob/master/CHANGELOG.md

选择好版本后进行安装

```
$ nvm install 8.2
```

查询当前使用的node版本

```
$ nvm ls
->       v8.2.1
node -> stable (-> v8.2.1) (default)
stable -> 8.2 (-> v8.2.1) (default)
iojs -> iojs- (-> N/A) (default)
```

```
$ node -v
v8.2.1
```

<font color="red">
node安装完成后，node包管理工具npm也随之安装完成了。
</font>

```
$ npm -v
5.3.0
```


### 安装vue.js

```
$ npm install vue
npm notice created a lockfile as package-lock.json. You should commit this file.
+ vue@2.4.2
added 1 package in 2.88s
```


### 安装cnpm命令

cnpm是淘宝对npm做的一个镜像，目的是提高软件包下载的速度。

cnpm官网：http://npm.taobao.org/

```
$ npm install -g cnpm --registry=https://registry.npm.taobao.org
```

<font color="red">
安装cnpm之后，所有使用npm命令的地方都可以使用cnpm命令代替。
</font>


### 安装vue的官方命令行工具

```
$ npm install --global vue-cli
```
或
```
$ npm install -g vue-cli
```

安装成功后会生成一个vue命令。

```
$ vue -V
2.8.2
```


### 使用vue命令创建项目

创建项目

```
$ vue init webpack my-first-vue-project

? Project name my-first-vue-project
? Project description my first vue project
? Author mumingv <mumingv@163.com>
? Vue build standalone
? Install vue-router? Yes
? Use ESLint to lint your code? No
? Setup unit tests with Karma + Mocha? No
? Setup e2e tests with Nightwatch? No

   vue-cli · Generated "my-first-vue-project".

   To get started:

     cd my-first-vue-project
     npm install
     npm run dev

   Documentation can be found at https://vuejs-templates.github.io/webpack
```

安装依赖并运行

```
$ npm install
$ npm run dev
```

运行成功后，默认会启动一个Web服务器

```
http://localhost:8080
```


### 常见问题

#### 重启电脑后node、npm和vue命令都不能使用了？

查询当前使用的版本，v8.2.1前面没有箭头指向，表示未选择node版本。

```
$ nvm ls
    	v8.2.1
node -> stable (-> v8.2.1) (default)
stable -> 8.2 (-> v8.2.1) (default)
iojs -> iojs- (-> N/A) (default)
```

执行nvm use命令解决。

```
$ nvm use 8.2
Now using node v8.2.1 (npm v5.3.0)
$ nvm ls
->       v8.2.1
node -> stable (-> v8.2.1) (default)
stable -> 8.2 (-> v8.2.1) (default)
iojs -> iojs- (-> N/A) (default)
```


## vue.js及相关工具介绍

### vue文件组成

webpack用于将.vue文件打包成.html、.css和.js文件，其中的.js文件就对应`new Vue({...})`创建的一个对象。

.vue文件的组成包含如下三个方面：

```
HTML: <template></template>
CSS: <style></style>
JS: <script></script>
```


### vue组件

vue组件就是一个vue文件，同时包含HTML、CSS和JS。


### 双向绑定

页面中的用户输入绑定到JS中的变量，而JS中的变量又绑定到页面中的输出。



## todolist项目学习













