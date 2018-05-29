# FAQ

## 如何在笔记中使用LaTex显示数学公式？

示例：[链接](http://123.56.21.232:8252/plugins/mathjax/)。

在html的head标签中引入如下js：

```
<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]}});</script>
<script async src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_CHTML"></script>
```

行内公式使用：\\(...\\) 或 $...$

整行公式使用：\\[ \\] 或 $$...$$

