# Nvm

## 参考手册

- [(线上) GitHub](https://github.com/creationix/nvm#usage)


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


## 命令列表

###### 

|命令 				|说明					|示例 				|
|-------------------|-----------------------|-------------------|
|nvm help 			|查看帮助 				|					|
|nvm ls 			|查看已安装的版本 			|					|
|nvm ls-remote 		|查看可用的版本 			|					|
|nvm install 		|安装指定的版本			|安装8.2版本：nvm install 8.2 	|




