bootstrap-typeahead是一款搜索自动补全插件

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 搜索自动补全 `form/autocomplete.html`（项目使用需要引入js）

<th:block th:include="include :: bootstrap-typeahead-js" />

| 属性              | 类型               | 默认值                                         | 描述                                                                                                                      |
| --------------- | ---------------- | ------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| source          | array, function  | [ ]                                         | 要查询的数据源。可能是一个字符串数组，一个具有name属性或函数的JSON对象数组。该函数接受两个参数， query 即输入字段中的值和 process 回调。该函数可以通过 process 回调的单个参数直接或异步返回数据源来同步使用。 |
| items           | number           | 8                                           | 在下拉列表中显示的最大项目数。也可以设置为“全部”                                                                                               |
| minLength       | number           | 1                                           | 触发自动填充建议之前所需的最小字符长度。您可以将其设置为0，因此即使在调用查找功能时没有文本时也会显示建议。                                                                  |
| showHintOnFocus | boolean          | false                                       | 一旦输入得到焦点，就可以在适用时显示提示。                                                                                                   |
| scrollHeight    | number, function | 0                                           | 可滚动父容器向下滚动的像素数（滚出视口）。                                                                                                   |
| matcher         | function         | case insensitive                            | 用于确定查询是否匹配项的方法。接受单个参数， item 用于测试查询。访问当前查询 this.query。true如果查询是匹配，则返回一个布尔值。                                              |
| sorter          | function         | exact match,case sensitive,case insensitive | 用于对自动完成结果进行排序的方法。接受单个参数， items 并具有类型头实例的范围。引用当前查询 this.query.                                                           |
| updater         | function         | returns selected item                       | 用于返回所选项目的方法。接受单个参数， item 并具有类型头实例的范围。                                                                                   |
| highlighter     | function         | highlights all default matches              | 用于突出显示自动完成结果的方法。接受单个参数， item 并具有类型头实例的范围。应该返回html                                                                       |
| displayText     | function         | item.name item                              | 用于获取源的项目的文本表示的方法。接受单个参数， item 并具有类型头实例的范围。应该返回一个String。                                                                 |
| autoSelect      | boolean          | true                                        | 允许您指定是否自动选择第一个建议。关闭自动选择也意味着如果没有选择 enter 或被 tab 击中，输入将不会被清除。                                                             |
| afterSelect     | function         | $.noop()                                    | 调用功能在选择一个项目后执行。它将当前活动项目置于参数中（如果有）。                                                                                      |
| delay           | integer          | 0                                           | 在查找之间增加延迟。                                                                                                              |
| addItem         | JSONobject       | false                                       | 将项目添加到列表的末尾，例如“新建条目”。例如，当在数据列表中找不到某个项目时，可以使用该对话框。                                                                       |
