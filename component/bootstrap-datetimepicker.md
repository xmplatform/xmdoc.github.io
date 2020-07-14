bootstrap-datetimepicker是一款时间插件（已经汉化）

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 日期与时间 `form/datetime.html`（项目使用需要引入css和js）

1、<th:block th:include="include :: datetimepicker-css" />  
2、<th:block th:include="include :: datetimepicker-js" />

| 属性                 | 默认值          | 描述                       | 备注                                                  |
| ------------------ | ------------ | ------------------------ | --------------------------------------------------- |
| format             | mm/dd/yyyy   | 日期格式                     | 任意时间日期格式组合搭配，满足不同需求 yyyy mm dd hh ii ss             |
| weekStart          | 0            | 一周从哪一天开始                 | 0（星期日）到6（星期六）                                       |
| startDate          | 无            | 开始时间                     | 可以选择的最早日期，将禁用所有较早日期                                 |
| endDate            | 无            | 结束时间                     | 可以选择的最晚日期，所有较迟的日期都将被禁用                              |
| daysOfWeekDisabled | []           | 每周禁用一天                   |                                                     |
| autoclose          | false        | 当选择一个日期之后是否立即关闭此日期时间选择器。 |                                                     |
| startView          | 2            | 日期时间选择器打开之后首先显示的视图       | 0 小时 1 天 2 月 3 年 4 十年                               |
| minView            | 0            | 日期时间选择器所能够提供的最精确的时间选择视图  | 0 小时 1 天 2 月 3 年 4 十年                               |
| maxView            | 4            | 日期时间选择器最高能展示的选择范围视图      | 0 小时 1 天 2 月 3 年 4 十年                               |
| todayBtn           | false        | 是否显示当前日期（今天）按钮           |                                                     |
| todayHighlight     | false        | 是否高亮当前日期                 |                                                     |
| keyboardNavigation | true         | 是否启用键盘方向键选择改变日期          |                                                     |
| language           | en           | 语言                       | zh-cn 中文 en 英文                                      |
| forceParse         | true         | 强制解析                     | 当选择器关闭的时候，是否强制解析输入框中的值                              |
| minuteStep         | 5            | 分钟选择视图，每5分钟一个间隔选择        | 只有minView设置 支持分钟，才能看到                               |
| pickerReferer      | default      |                          | 没有特殊要求，无序设置                                         |
| pickerPosition     | bottom-right | 时间选择器窗口的位置               | bottom-left左下 bottom-right右下 top-left左上 top-right左下 |
| viewSelect         | 取minView的值   | 视图选择                     | decade year month day hour                          |
| showMeridian       | false        | 是否为日视图和小时视图启用子午线视图       |                                                     |
| initialDate        | new Date()   | 初始日期。                    | 默认是现在，您可以指定昨天或今天……                                  |
