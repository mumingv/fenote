# aitree

## FAQ

### 如何在提交表单时不使用表单默认的action，而是采用ajax请求的方式获取数据？


### 如何取消回车自动触发的表单提交？

当表单中只有一个`<input type="text"/>`时，回车会默认触发表单提交。

在表单中增加一个空的<input/>标签，可以解决回车默认触发表单。修改后的表单如下：

```
<form class="search-form">
    <input style="display:none" />
    <input type="text" class="search-text" autocomplete="off" />
    <input type="button" class="search-button" value="" />
</form>
```


