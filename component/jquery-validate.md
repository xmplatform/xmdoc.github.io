jQuery Validate 插件为表单提供了强大的验证功能，让客户端表单验证变得更简单，同时提供了大量的定制选项，满足应用程序各种需求。 该插件捆绑了一套有用的验证方法，包括 URL 和电子邮件验证，同时提供了一个用来编写用户自定义方法的 API。

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 表单验证 `form/validate.html`

默认校验规则。

| 属性                 | 描述                                                     |
| ------------------ | ------------------------------------------------------ |
| required:true      | 必须输入的字段                                                |
| remote:"/action"   | 使用ajax方法调用action验证输入值                                  |
| email:true         | 必须输入正确格式的电子邮件                                          |
| url:true           | 必须输入正确格式的网址                                            |
| date:true          | 必须输入正确格式的日期。日期校验 ie6 出错，慎用                             |
| dateISO:true       | 必须输入正确格式的日期（ISO），例如：2009-06-23，1998/01/22。只验证格式，不验证有效性 |
| number:true        | 必须输入合法的数字（负数，小数）                                       |
| digits:true        | 必须输入整数                                                 |
| creditcard:        | 必须输入合法的信用卡号                                            |
| equalTo:"#field"   | 输入值必须和 #field 相同                                       |
| accept:            | 输入拥有合法后缀名的字符串（上传文件的后缀）                                 |
| maxlength:5        | 输入长度最多是 5 的字符串（汉字算一个字符）                                |
| minlength:10       | 输入长度最小是 10 的字符串（汉字算一个字符）                               |
| rangelength:[5,10] | 输入长度必须介于 5 和 10 之间的字符串（汉字算一个字符）                        |
| range:[5,10]       | 输入值必须介于 5 和 10 之间                                      |
| max:5              | 输入值不能大于 5                                              |
| min:10             | 输入值不能小于 10                                             |
| isIp:true          | IP地址验证                                                 |
| isPhone:true       | 手机号码验证                                                 |
| isTel:true         | 电话号码验证                                                 |
| isName:true        | 姓名验证                                                   |
| isUserName:true    | 用户名验证                                                  |
| isIdentity:true    | 身份证验证                                                  |
| isBirth:true       | 出生日期验证                                                 |

内置验证方式。

| 名称                              | 类型      | 描述                                      |
| ------------------------------- | ------- | --------------------------------------- |
| required()                      | Boolean | 必填验证元素                                  |
| required(dependency-expression) | Boolean | 必填元素依赖于表达式的结果                           |
| required(dependency-callback)   | Boolean | 必填元素依赖于回调函数的结果                          |
| remote(url)                     | Boolean | 请求远程校验。url 通常是一个远程调用方法                  |
| minlength(length)               | Boolean | 设置最小长度                                  |
| maxlength(length)               | Boolean | 设置最大长度                                  |
| rangelength(range)              | Boolean | 设置一个长度范围 [min,max]                      |
| min(value)                      | Boolean | 设置最小值                                   |
| max(value)                      | Boolean | 设置最大值                                   |
| email()                         | Boolean | 验证电子邮箱格式                                |
| range(range)                    | Boolean | 设置值的范围                                  |
| url()                           | Boolean | 验证 URL 格式                               |
| date()                          | Boolean | 验证日期格式（类似 30/30/2008 的格式，不验证日期准确性只验证格式） |
| dateISO()                       | Boolean | 验证 ISO 类型的日期格式                          |
| dateDE()                        | Boolean | 验证德式的日期格式（29.04.1994 或 1.1.2006）        |
| number()                        | Boolean | 验证十进制数字（包括小数的）                          |
| digits()                        | Boolean | 验证整数                                    |
| creditcard()                    | Boolean | 验证信用卡号                                  |
| accept(extension)               | Boolean | 验证相同后缀名的字符串                             |
| equalTo(other)                  | Boolean | 验证两个输入框的内容是否相同                          |
| phoneUS()                       | Boolean | 验证美式的电话号码                               |

验证的触发方式修改。

| 触发方式         | 类型      | 默认值   | 描述                                                    |
| ------------ | ------- | ----- | ----------------------------------------------------- |
| onsubmit     | Boolean | true  | 提交时验证。设置为 false 就用其他方法去验证                             |
| onfocusout   | Boolean | true  | 失去焦点时验证（不包括复选框/单选按钮）                                  |
| onkeyup      | Boolean | true  | 在 keyup 时验证                                           |
| onclick      | Boolean | true  | 在点击复选框和单选按钮时验证                                        |
| focusInvalid | Boolean | true  | 提交表单后，未通过验证的表单（第一个或提交之前获得焦点的未通过验证的表单）会获得焦点            |
| focusCleanup | Boolean | false | 如果是 true 那么当未通过验证的元素获得焦点时，移除错误提示。避免和 focusInvalid 一起用 |
