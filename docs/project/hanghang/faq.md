# FAQ

## Q: 如何将80端口映射到6150端口？

```
iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 6150
```

参考资料：
- [非root用户如何使用80端口启动tomcat](https://yq.aliyun.com/articles/514714)
