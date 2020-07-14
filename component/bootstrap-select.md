bootstrap.select.js是一款下拉框插件

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 下拉框 `form/select.html`（项目使用需要引入css和js）

1、<th:block th:include="include :: bootstrap-select-css" />  
2、<th:block th:include="include :: bootstrap-select-js" />

| 属性                    | 类型                           | 默认值                | 描述                                                                                                                                                             |
| --------------------- | ---------------------------- | ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| actionsBox            | bool                         | false              | 当设置为true，增加了两个按钮，下拉菜单的顶部（全选和取消全选）                                                                                                                              |
| container             | string                       | false              | 当设置为一个字符string，追加选择一个特定的元素或选择器，例如 container: 'body'                                                                                                            |
| countSelectedText     | string                       | function           | 设置当selectedTextFormat是显示文本的格式count或count > #。{0} 是所选择的量。{1}是用于选择的总可用。当设定为一个函数，第一个参数是所选择的选项的数目，并且第二个是选项的总数。该函数必须返回一个字符string                                    |
| deselectAllText       | string                       | 'Deselect All'     | 当取消选择所有选项按钮上的文本actionsBox被启用                                                                                                                                   |
| dropdownAlignRight    | bool 'auto'                  | false              | 对齐菜单，而不是左右。如果设置为'auto'，如果在左对齐没有余地菜单的全宽度的菜单会自动右对齐                                                                                                               |
| dropupAuto            | bool                         | true               | 进行检查以查看其具有更多的空间，上方或下方。如果dropup有足够的空间完全打开正常，但上面有更大的空间，在dropup仍能正常打开。否则，就变成了dropup。如果dropupAuto设置为false，dropups必须手动调用                                            |
| header                | string                       | false              | 增加了菜单的顶部的头部; 默认包含关闭按钮                                                                                                                                          |
| hideDisabled          | bool                         | false              | 从菜单中删除禁用的选项和optgroups data-hide-disabled: true                                                                                                                 |
| iconBase              | string                       | 'glyphicon'        | 将基地使用不同的图标字体代替Glyphicons。如果改变iconBase，你也可能要更改tickIcon，以防新的图标字体使用了不同的命名方案                                                                                       |
| liveSearch            | bool                         | false              | 当设置为true，增加了一个搜索框的下拉selectpicker的顶部                                                                                                                            |
| liveSearchNormalize   | bool                         | false              | 设置liveSearchNormalize以true允许不区分重音的搜索                                                                                                                           |
| liveSearchPlaceholder | string                       | null               | 当设置为一个字符string，一个占位符属性等于该字符string将被添加到实况搜索输入                                                                                                                   |
| liveSearchStyle       | string                       | 'contains'         | 当设置为'contains'，搜索将显示包含搜索到的文本选项。例如，搜索，返回鸭都为PL PL E，PL嗯，和PL antain。当设置为'startsWith'，寻找PL只会返回PL UM和PL antain                                                      |
| maxOptions            | integer                      | false              | 当设置为一个integer ，并在多选择，所选选项的数量不能超过给定值。该选项还可以存在作为数据属性为optgroup，在这种情况下，它仅适用于optgroup                                                                               |
| maxOptionsText        | string                       | function           | 启用maxOptions时所显示的文本，并为给定的方案选项的最大数量已被选定。如果使用的功能，它必须返回一个数组。阵列[0]是当maxOptions被施加到整个选择元件使用的文本。阵列[1]是当maxOptions上的OPTGROUP用于使用的文本。如果使用字符string，相同的文字用于元素和OPTGROUP两者 |
| mobile                | bool                         | false              | 当设置为true，使能选择菜单中的设备的本机菜单                                                                                                                                       |
| multipleSeparator     | string                       | ', '               | 坐落在分隔所选选项的按钮显示的字符                                                                                                                                              |
| noneSelectedText      | string                       | 'Nothing selected' | 当多个选择时所显示的文本没有选择的选择                                                                                                                                            |
| selectAllText         | string                       | 'Select All'       | 当选择了所有选项，按钮上的文本actionsBox被启用                                                                                                                                   |
| selectedTextFormat    | 'values' 'static' 'count'    | 'values'           | 指定选择如何显示有多个选择。'values'显示所选择的选项（由分隔的列表multipleSeparator。'static'简单地显示所述选择元件的标题。'count'显示所选选项的总数量。'count > x'行为类似于'values'直到所选选项的数目大于x;在此之后，它的行为象'count'         |
| selectOnTab           | bool                         | false              | 当设置为true，对待像selectpicker下拉列表中输入或空格字符制表符                                                                                                                        |
| showContent           | bool                         | true               | 当设置为true，显示与该按钮选择的选项（一个或多个）相关联的自定义的HTML。当设置为false，期权价值将被显示                                                                                                     |
| showIcon              | bool                         | true               | 当设置为true，与在按钮选择的选项（一个或多个）相关联的显示的图标（一个或多个）                                                                                                                      |
| showSubtext           | bool                         | false              | 当设置为true与所述按钮选择的选项相关联，显示潜台词                                                                                                                                    |
| showTick              | bool                         | false              | show（没有的项目上选择的选项勾选multiple属性）                                                                                                                                  |
| size                  | 'auto' integer false         | 'auto'             | 当设置为'auto'，菜单始终打开，以显示尽可能多的项目窗口将允许在没有被切断。当设置为integer 时，菜单将显示项目的给定数量，即使下拉被切断。当设置为false，菜单会一直显示所有项目                                                               |
| style                 | string null                  | null               | 当设置为一个字符string，添加值到该按钮的风格                                                                                                                                      |
| tickIcon              | string null                  | 'glyphicon-ok'     | 设置要使用的图标旁边显示的“滴答”来选择的选项                                                                                                                                        |
| title                 | string                       | null               | null                                                                                                                                                           |
| width                 | 'auto' 'fit' css-width false | false              | 当设置为auto，所述selectpicker的宽度被自动调节，以适应最宽的选项。当设置为一个css-宽度，所述selectpicker的宽度内联强制为给定值。当设置为false，所有宽度信息被删除                                                            |
| windowPadding         | integer array                | 0                  | 这是在该窗口中有一个下拉菜单中不应该涉及的领域情况下非常有用-例如一个固定的头。当设置为一个integer ，同样填充将被添加到四面八方。可替代地，一个integer 数组可以在格式来使用[top, right, bottom, left]                                       |

```javascript
// selectpicker 常用方法
$('#id').selectpicker('val');                      // 取值
$('#id').selectpicker('val', 'RuoYi');             // 单个赋值
$('#id').selectpicker('val', ['Admin','RuoYi']);   // 多选赋值
$('#id').selectpicker('selectAll');                // 全选
$('#id').selectpicker('deselectAll');              // 反选
$('#id').selectpicker('render');                   // 渲染
$('#id').selectpicker('refresh');                  // 刷新
$('#id').prop('disabled', true);                   // 禁用
$('#id').prop('disabled', false);                  // 启用
$('#id').selectpicker('toggle');                   // 切换
$('#id').selectpicker('hide');                     // 隐藏
$('#id').selectpicker('show');                     // 显示
$('#id').selectpicker('destroy');                  // 销毁
$('#id').selectpicker('mobile');                   // 适应手机模式
<!--  事件监听show.bs.selectshown.bs.selecthide.bs.selecthidden.bs.selectloaded.bs.selectrendered.bs.selectrefreshed.bs.selectchanged.bs.select
-->
$('#id').on('changed.bs.select', function (e, clickedIndex, isSelected, previousValue) {
  // 处理自己的业务
});
```
