bootstrap-suggest这是一个基于bootstrap按钮式下拉菜单组件的搜索建议插件

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 搜索自动补全 `form/autocomplete.html`（项目使用需要引入js）

<th:block th:include="include :: bootstrap-suggest-js" />

| 属性                   | 默认值                            | 描述                                                                                                                                                                                                                     |
| -------------------- | ------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| url                  | null                           | 请求数据的 URL 地址                                                                                                                                                                                                           |
| jsonp                | null                           | 设置此参数名，将开启jsonp功能，否则使用json数据结构                                                                                                                                                                                         |
| data                 | []                             | 提示所用的数据，注意格式                                                                                                                                                                                                           |
| indexId              | 0                              | 每组数据的第几个数据，作为input输入框的 data-id，设为 -1 且 idField 为空则不设置此值                                                                                                                                                                |
| indexKey             | 0                              | 每组数据的第几个数据，作为input输入框的内容                                                                                                                                                                                               |
| idField              | ''                             | 每组数据的哪个字段作为 data-id，优先级高于 indexId 设置（推荐）                                                                                                                                                                               |
| keyField             | ''                             | 每组数据的哪个字段作为输入框内容，优先级高于 indexKey 设置（推荐）                                                                                                                                                                                 |
| autoSelect           | true                           | 键盘向上/下方向键时，是否自动选择值                                                                                                                                                                                                     |
| allowNoKeyword       | TRUE                           | 是否允许无关键字时请求数据                                                                                                                                                                                                          |
| getDataMethod        | 'firstByUrl'                   | 获取数据的方式，url：一直从url请求；data：从 options.data 获取；firstByUrl：第一次从Url获取全部数据，之后从options.data获取                                                                                                                                 |
| delayUntilKeyup      | false                          | 获取数据的方式 为 firstByUrl 时，是否延迟到有输入时才请求数据                                                                                                                                                                                  |
| ignorecase           | false                          | 前端搜索匹配时，是否忽略大小写                                                                                                                                                                                                        |
| effectiveFields      | []                             | 有效显示于列表中的字段，非有效字段都会过滤，默认全部有效                                                                                                                                                                                           |
| effectiveFieldsAlias | {}                             | 有效字段的别名对象，用于 header 的显示                                                                                                                                                                                                |
| searchFields         | []                             | 有效搜索字段，从前端搜索过滤数据时使用，但不一定显示在列表中。effectiveFields 配置字段也会用于搜索过滤                                                                                                                                                            |
| twoWayMatch          | true                           | 是否双向匹配搜索。为 true 即输入关键字包含或包含于匹配字段均认为匹配成功，为 false 则输入关键字包含于匹配字段认为匹配成功                                                                                                                                                    |
| multiWord            | false                          | 以分隔符号分割的多关键字支持                                                                                                                                                                                                         |
| separator            | ','                            | 多关键字支持时的分隔符，默认为半角逗号                                                                                                                                                                                                    |
| delay                | 300                            | 搜索触发的延时时间间隔，单位毫秒                                                                                                                                                                                                       |
| emptyTip             | ''                             | 查询为空时显示的内容，可为 html                                                                                                                                                                                                     |
| searchingTip         | '搜索中...'                       | ajax 搜索时显示的提示内容，当搜索时间较长时给出正在搜索的提示                                                                                                                                                                                      |
| hideOnSelect         | false                          | 鼠标从列表单击选择了值时，是否隐藏选择列表                                                                                                                                                                                                  |
| autoDropup           | false                          | 选择菜单是否自动判断向上展开。设为 true，则当下拉菜单高度超过窗体，且向上方向不会被窗体覆盖，则选择菜单向上弹出                                                                                                                                                             |
| autoMinWidth         | false                          | 是否自动最小宽度，设为 false 则最小宽度不小于输入框宽度                                                                                                                                                                                        |
| showHeader           | false                          | 是否显示选择列表的 header。为 true 时，有效字段大于一列则显示表头                                                                                                                                                                                |
| showBtn              | true                           | 是否显示下拉按钮                                                                                                                                                                                                               |
| inputBgColor         | ''                             | 输入框背景色，当与容器背景色不同时，可能需要该项的配置                                                                                                                                                                                            |
| inputWarnColor       | 'rgba(255,0,0,.1)'             | 输入框内容不是下拉列表选择时的警告色                                                                                                                                                                                                     |
| listStyle            | 默认参考描述                         | 列表的样式控制 { 'padding-top': 0, 'max-height': '375px', 'max-width': '800px', 'overflow': 'auto', 'width': 'auto', 'transition': '0.3s', '-webkit-transition': '0.3s', '-moz-transition': '0.3s', '-o-transition': '0.3s' } |
| listAlign            | 'left'                         | 提示列表对齐位置，left/right/auto                                                                                                                                                                                               |
| listHoverStyle       | 'background: #07d; color:#fff' | 提示框列表鼠标悬浮的样式                                                                                                                                                                                                           |
| listHoverCSS         | 'jhover'                       | 提示框列表鼠标悬浮的样式名称                                                                                                                                                                                                         |
| clearable            | false                          | 是否可清除已输入的内容                                                                                                                                                                                                            |
| keyLeft              | 37                             | 向左方向键，不同的操作系统可能会有差别，则自行定义                                                                                                                                                                                              |
| keyUp                | 38                             | 向上方向键                                                                                                                                                                                                                  |
| keyRight             | 39                             | 向右方向键                                                                                                                                                                                                                  |
| keyDown              | 40                             | 向下方向键                                                                                                                                                                                                                  |
| keyEnter             | 13                             | 回车键                                                                                                                                                                                                                    |
| fnProcessData        | processData                    | 格式化数据的方法，返回数据格式参考 data 参数                                                                                                                                                                                              |
| fnGetData            | getData                        | 获取数据的方法，无特殊需求一般不作设置                                                                                                                                                                                                    |
| fnAdjustAjaxParam    | null                           | 调整 ajax 请求参数方法，用于更多的请求配置需求。如对请求关键字作进一步处理、修改超时时间等                                                                                                                                                                       |
| fnPreprocessKeyword  | null                           | 搜索过滤数据前，对输入关键字作进一步处理方法。注意，应返回字符串                                                                                                                                                                                       |

```javascript
// suggest 常用方法
$("input#test").bsSuggest("disable");    // 禁用提示
$("input#test").bsSuggest("enable");     // 启用提示
$("input#test").bsSuggest("destroy");    // 销毁插件
$("input#test").bsSuggest("version");    // 查看版本

<!--  事件监听onDataRequestSuccess  // 当 AJAX 请求数据成功时触发，并传回结果到第二个参数
onSetSelectValue      // 当从下拉菜单选取值时触发，并传回设置的数据到第二个参数
onUnsetSelectValue    // 当设置了 idField，且自由输入内容时触发（与背景警告色显示同步）
onShowDropdown        // 下拉菜单显示时触发
onHideDropdown        // 拉菜单隐藏式触发
-->
$("#test").bsSuggest('init', {
    url: "/rest/sys/getuserlist?keyword=",
    effectiveFields: ["userName", "email"],
    searchFields: [ "shortAccount"],
    effectiveFieldsAlias:{userName: "姓名"},
    clearable: true,
    idField: "userId",
    keyField: "userName"
}).on('onDataRequestSuccess', function (e, result) {
    console.log('onDataRequestSuccess: ', result);
}).on('onSetSelectValue', function (e, selectedData, selectedRawData) {
    console.log('onSetSelectValue: ', e.target.value, selectedData, selectedRawData);
}).on('onUnsetSelectValue', function () {
    console.log('onUnsetSelectValue');
}).on('onShowDropdown', function (e, data) {
    console.log('onShowDropdown', e.target.value, data);
}).on('onHideDropdown', function (e, data) {
    console.log('onHideDropdown', e.target.value, data);
});
```
