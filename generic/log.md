由于调试或者基于未来可能错误的考虑，代码中会留有不同日志级别的输出，以便于在特定情况下输出更详细的错误信息，但是生产环境通常是不能重启的，因此就有动态修改日志级别的需求。通过访问某个url即可改变日志级别，从而在不重启服务的情况下，查看到详细的错误信息，这个对于排错非常有意义。

**查看当前日志级别**


```html
[baseUrl]/log/level/test
[baseUrl]/log/level/test?packageName=[包名]
```

**动态修改当前日志级别**

[日志级别]枚举值为：OFF,FATAL,ERROR,WARN,INFO,DEBUG,TRACE,ALL

```html
[baseUrl]/log/level/[日志级别]
```
