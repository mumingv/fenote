# 数据结构

## Queue 队列 - 数组实现

### 示例：后进前出

```
> queue = []
[]
> queue.push('apple')
1
> queue.push('orange')
2
> queue.push('banana')
3
> queue.shift()
'apple'
> queue.shift()
'orange'
> queue.shift()
'banana'
> queue.length
0
```


### 示例：前进后出

```
> queue = []
[]
> queue.unshift('apple')
1
> queue.unshift('orange')
2
> queue.unshift('banana')
3
> queue.pop()
'apple'
> queue.pop()
'orange'
> queue.pop()
'banana'
> queue.length
0
```


### 参考资料

- [MDN之Array](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)


## Stack 堆栈 - 数组实现

### 示例：后进后出

```
> stack = []
[]
> stack.push('apple')
1
> stack.push('orange')
2
> stack.push('banana')
3
> stack.pop()
'banana'
> stack.pop()
'orange'
> stack.pop()
'apple'
> stack.length
0
```


### 示例：前进前出

```
> stack = []
[]
> stack.unshift('apple')
1
> stack.unshift('orange')
2
> stack.unshift('banana')
3
> stack.shift()
'banana'
> stack.shift()
'orange'
> stack.shift()
'apple'
> stack.length
0
```


### 参考资料

- [MDN之Array](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array)


## Set 集合

### 参考资料

- [MDN之Set](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Set)


## Map 映射

### 参考资料

- [MDN之Map](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Map)


## 参考资料

- [链表是一种数据结构还是数据类型？](https://www.zhihu.com/question/55419163)

