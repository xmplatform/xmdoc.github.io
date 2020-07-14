bootstrap-duallistbox是一款双重列表框插件

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 左右互选组件 `form/duallistbox.html`（项目使用需要引入css和js）

1、<th:block th:include="include :: bootstrap-duallistbox-css" />  
2、<th:block th:include="include :: bootstrap-duallistbox-js" />

| 属性                      | 默认值                     | 描述                                                                                                                                                                           |
| ----------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| bootstrap2Compatible    | false                   | 兼容bootstrap2                                                                                                                                                                 |
| filterTextClear         | 'show all'              | 清空过滤条件按钮的文本                                                                                                                                                                  |
| filterPlaceHolder       | 'Filter'                | 过滤条件的input框的placeholder                                                                                                                                                      |
| moveSelectedLabel       | 'Move selected'         | 添加选中option按钮的label                                                                                                                                                           |
| moveAllLabel            | 'Move all'              | 添加全部option按钮的label                                                                                                                                                           |
| removeSelectedLabel     | 'Remove selected'       | 移除选中option按钮的label                                                                                                                                                           |
| removeAllLabel          | 'Remove all'            | 移除全部option按钮的label                                                                                                                                                           |
| moveOnSelect            | true                    | 是否移动选中的option:为false时,moveSelected和removeSelected的按钮显示生效:默认为true;为true只能光标连续选取,松开鼠标,选中的项会移动;为false则可配合键盘的Ctrl和Shift使用,点击moveSelectedLabel和removeSelectedLabel的按钮, option才会移动 |
| preserveSelectionOnMove | false                   | 'moved'或'all'时，展示移动到target列表中的元素（背景色显示）。配合moveOnSelect为false使用                                                                                                               |
| selectedListLabel       | false                   | 已选中list的label                                                                                                                                                                |
| nonSelectedListLabel    | false                   | 未选中list的label                                                                                                                                                                |
| helperSelectNamePostfix | '_helper'               | 为selector的name的后缀为_helper,朱选中的list后面拼接1,已选中的拼接2:也可通过 setHelperSelectNamePostfix(value, refresh)方法修改                                                                          |
| selectorMinimalHeight   | 100                     | selector的最小高度,小于元素的height()则高度的值为height()                                                                                                                                    |
| showFilterInputs        | true                    | 是否显示过滤的nput输入框,默认tue显示;为fase则过滤相关的内容不起作用、不显示                                                                                                                                 |
| nonSelectedFilter       | ''                      | 未选中option的过滤条件,默认为空字符串,也可用正则方式,例如:ion([7-9][1]0-2)过滤7、8、9、10、11、12                                                                                                           |
| selectedFilter          | ''                      | 已选中option的过滤条件,默认为空字符串;参考:nonSelectedFilter;-般不设置已选中的过滤条件,会导致某些选中的项不在已选中option的过滤条件范围内,无法显示                                                                                  |
| infoText                | 'Showing all {0}'       | 未输入过滤条件时,选中/未选中option共几项                                                                                                                                                     |
| infoTextFiltered        | 'Filtered {0} from {1}' | 过滤信息,默认< span class="label label-Warning">Filtered{0} from {1}。从m项中筛选n项                                                                                                      |
| infoTextEmpty           | 'Empty list'            | 当筛选条件为'',且选中/未选中列表无option时显示的内容                                                                                                                                              |
| filterOnValues          | false                   | 过滤选项的值                                                                                                                                                                       |
| eventMoveoverride       | false                   | 设置为true,可自定义moveSelected的事件                                                                                                                                                  |
| eventMoveAlloverride    | false                   | 设置为true,可自定义moveAll的事件                                                                                                                                                       |
| eventRemoveOverride     | false                   | 设置为true,可自定义removeSelectecd的事件                                                                                                                                               |
| eventRemoveAlloverride  | false                   | 设置为true,可自定义removeAll的事件                                                                                                                                                     |

Method说明。

| 方法名                                        | 描述                            |
| ------------------------------------------ | ----------------------------- |
| refresh()                                  | 更新UI插件元素                      |
| destroy()                                  | 恢复原始元素                        |
| getContainer()                             | 获取容器元素                        |
| setBootstrap2Compatible(value, refresh)    | 更改 bootstrap2Compatible 参数    |
| setFilterTextClear(value, refresh)         | 更改 filterTextClear 参数         |
| setFilterPlaceHolder(value, refresh)       | 更改 filterPlaceHolder 参数       |
| setMoveSelectedLabel(value, refresh)       | 更改 moveSelectedLabel 参数       |
| setMoveAllLabel(value, refresh)            | 更改 moveAllLabel 参数            |
| setRemoveSelectedLabel(value, refresh)     | 更改 removeSelectedLabel 参数     |
| setRemoveAllLabel(value, refresh)          | 更改 removeAllLabel 参数          |
| setMoveOnSelect(value, refresh)            | 更改 moveOnSelect 参数            |
| setPreserveSelectionOnMove(value, refresh) | 更改 preserveSelectionOnMove 参数 |
| setSelectedListLabel(value, refresh)       | 更改 selectedListLabel 参数       |
| setNonSelectedListLabel(value, refresh)    | 更改 nonSelectedListLabel 参数    |
| setHelperSelectNamePostfix(value, refresh) | 更改 helperSelectNamePostfix 参数 |
| setSelectOrMinimalHeight(value, refresh)   | 更改 selectorMinimalHeight 参数   |
| setShowFilterInputs(value, refresh)        | 更改 showFilterInputs 参数        |
| setNonSelectedFilter(value, refresh)       | 更改 nonSelectedFilter 参数       |
| setSelectedFilter(value, refresh)          | 更改 selectedFilter 参数          |
| setInfoText(value, refresh)                | 更改 infoText 参数                |
| setInfoTextFiltered(value, refresh)        | 更改 infoTextFiltered 参数        |
| setInfoTextEmpty(value, refresh)           | 更改 infoTextEmpty 参数           |
| setFilterOnValues(value, refresh)          | 更改 filterOnValues 参数          |
