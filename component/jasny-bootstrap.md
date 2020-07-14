jasny.js是一个功能扩展插件（含文件上传）

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 功能扩展 `form/jasny.html`（项目使用需要引入css和js）

1、<th:block th:include="include :: jasny-bootstrap-css" />  
2、<th:block th:include="include :: jasny-bootstrap-js" />

| 属性   | 类型     | 默认值  | 描述       |
| ---- | ------ | ---- | -------- |
| name | string | 当前元素 | 使用指定元素设置 |

```
$('#id').fileinput(options)     // 初始
$('#id').fileinput('clear')     // 清除
$('#id').fileinput('reset')     // 重置

<!--  事件监听change.bs.fileinput clear.bs.fileinputreset.bs.fileinput 
-->
$('#id').on('change.bs.fileinput ', function (e) {
  // 处理自己的业务
});
```
