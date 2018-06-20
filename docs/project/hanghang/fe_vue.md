# 成长记录Vue

## 2018-06-20：创建项目&健康管理

### 创建项目

###### 链接：[GitHub](https://github.com/mumingv/hanghang/commit/1cb43562f8941211236016797d5c51b5bb46d2ef)

```
vue init webpack growth
```

### 健康管理

#### 安装组件：element-ui

```
cnpm i element-ui -S
```

使用前需要在`main.js`中进行引入。

```
import ElementUI from 'element-ui';
import 'element-ui/lib/theme-chalk/index.css';

Vue.use(ElementUI);
```

#### 安装组件：axios

```
cnpm i axios -S
```

#### 检查结果页面

###### 链接：[GitHub](https://github.com/mumingv/hanghang/commit/fa778c5b7c52af1d40d7ba0dd2bda8d8b943869c)


## 2018-06-20：部署项目

### 部署脚本

```
$ cat run.sh 
#!/bin/bash

npm run build
rm -rf /home/work/odp/webroot/hanghang/*
cp -r ./dist/* /home/work/odp/webroot/hanghang/
```


### Nginx配置

```
# 主页路由
location = /hanghang/index.html {
    root            /home/work/odp/webroot;
}
location = / {
    rewrite ^(.*)$ /hanghang/index.html;
}

location ~ \.(js|css|gif|jpeg|png|woff|woff2|ttf) {
    root            /home/work/odp/webroot/hanghang;
}
```


## 其他信息

- [数据库](#docs/project/hanghang_db)



