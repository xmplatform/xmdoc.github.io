select2.js是一款下拉框插件

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 下拉框 `form/select.html`（项目使用需要引入css和js）

1、<th:block th:include="include :: select2-css" />  
2、<th:block th:include="include :: select2-js" />

| 属性                      | 类型       | 默认值   | 描述                                                          |
| ----------------------- | -------- | ----- | ----------------------------------------------------------- |
| data                    | Array    | Null  | 数据集合，基础数据格式{id:"", text:"", selected: true, disabled: true} |
| width                   | string   | 空     | 宽度                                                          |
| style                   | string   | 空     | 样式                                                          |
| ajax                    | object   | null  | Ajax请求数据                                                    |
| minimumResultsForSearch | Integer  | null  | 设置支持搜索的最小集合，设置为负数，隐藏搜索框                                     |
| minimumInputLength      | Integer  | 空     | 输入指定长度字符后开始搜索                                               |
| multiple                | boolean  | false | 是否多选，默认单选                                                   |
| maximumSelectionLength  | Integer  | 空     | 支持最大的选择数量，int/function                                      |
| maximumInputLength      | Integer  | 空     | 支持搜索的最大字符数                                                  |
| placeholder             | String   | 空     | 选择提示                                                        |
| allowClear              | Boolean  | false | 是否显示清除按钮，只有设置了placeholder才有效                                |
| closeOnSelect           | Boolean  | true  | 是否选中后关闭选择框，默认true                                           |
| templateSelection       | callback | 空     | 选中项样式                                                       |
| templateResult          | callback | 空     | 选项样式                                                        |
| matcher                 | callback | 空     | 过滤选项集合                                                      |
| sorter                  | callback | 空     | 选项结果集排序                                                     |
| theme                   | String   | 空     | 主题，可以设置bootstrap主题                                          |
| tags                    | Boolean  | 空     | 是否可动态创建选项                                                   |
| tokenSeparators         | Array    | 空     | 输入时使用分隔符创建新选项                                               |
| createTag               | callback | 空     | 创建新标签                                                       |
| insertTag               | callback | 空     | 在选项集合后插入标签                                                  |
| disabled                | boolean  | false | 是否失效                                                        |
| debug                   | boolean  | false | 是否开启debug                                                   |

```javascript
// select2 常用方法
$('#id').select2('val');                            // 取值
$("#id").select2("val", ["RuoYi"]);                 // 单个赋值
$("#id").val(["RuoYi"]).trigger("change");          // 单个赋值
$('#id').val(['Admin', 'RuoYi']).trigger("change"); // 多个赋值
$("#id").select2("open");                           // 打开下拉框
$("#id").select2("close");                          // 关闭下拉框
$('#id').prop('disabled', true);                    // 禁用
$('#id').prop('disabled', false);                   // 启用
$('#id').select2('destroy');                        // 销毁
<!--  事件监听change change.select2select2:closing select2:close select2:opening select2:openselect2:selecting select2:select select2:unselecting select2:unselect
-->
$('#id').on('select2:select', function (e) {
  // 处理自己的业务
});
```
