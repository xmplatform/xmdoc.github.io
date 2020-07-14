layer是一款web弹层组

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 日期与时间 `modal/layer.html`

| 属性         | 默认值                  | 描述           | 备注                                                                                                                    |
| ---------- | -------------------- | ------------ | --------------------------------------------------------------------------------------------------------------------- |
| type       | 0                    | 基本层类型        | layer提供了5种层类型。可传入的值有：0（信息框，默认）1（页面层）2（iframe层）3（加载层）4（tips层）。 若你采用layer.open({type: 1})方式调用，则type为必填项（信息框除外）          |
| title      | '信息'                 | 标题           | title支持三种类型的值，若你传入的是普通的字符串，那么只会改变标题文本；若你还需要自定义标题区域样式，那么你可以title: ['文本', 'font-size:18px;']，如果你不想显示标题栏，你可以title: false |
| content    | ''                   | 内容           | content可传入的值是灵活多变的，不仅可以传入普通的html内容，还可以指定DOM，更可以随着type的不同而不同。                                                          |
| skin       | ''                   | 样式类名         | skin不仅允许你传入layer内置的样式class名，还可以传入您自定义的class名。意味着你可以借助skin轻松完成不同的风格定制。目前layer内置的skin有：layui-layer-lan layui-layer-molv |
| area       | 'auto'               | 宽高           | 在默认状态下，layer是宽高都自适应的，但当你只想定义宽度时，你可以area: '500px'，高度仍然是自适应的。当你宽高都要定义时，你可以area: ['500px', '300px']                      |
| offset     | 垂直水平居中               | 坐标           | offset默认情况下不用设置。但如果你不想垂直水平居中 offset: ['100px', '50px']同时定义top、left坐标                                                  |
| icon       | -1（信息框）              | 图标           | 息框默认不显示图标。当你想显示图标时，默认皮肤可以传入0-6如果是加载层，可以传入0-2                                                                          |
| btn        | '确认'                 | 按钮           | 信息框模式时，btn默认是一个确认按钮，其它层类型则默认不显示，加载层和tips层则无效。当您只想自定义一个按钮时，你可以btn: '我知道了'，当你要定义两个按钮时，你可以btn: ['yes', 'no']。            |
| btnAlign   | r                    | 按钮排列         | 你可以快捷定义按钮的排列位置，btnAlign的默认值为r，即右对齐。btnAlign: 'l' 按钮左对齐 btnAlign: 'c' 按钮居中对齐 btnAlign: 'r' 按钮右对齐。默认值，不用设置              |
| closeBtn   | 1                    | 关闭按钮         | layer提供了两种风格的关闭按钮，可通过配置1和2来展示，如果不显示，则closeBtn: 0                                                                      |
| shade      | 0.3                  | 遮罩           | 即弹层外区域。默认是0.3透明度的黑色背景（'#000'）。如果你想定义别的颜色，可以shade: [0.8, '#393D49']；如果你不想显示遮罩，可以shade: 0                               |
| shadeClose | false                | 是否点击遮罩关闭     | 如果你的shade是存在的，那么你可以设定shadeClose来控制点击弹层外区域关闭。                                                                          |
| time       | 0                    | 自动关闭所需毫秒     | 默认不会自动关闭。当你想自动关闭时，可以time: 5000，即代表5秒后自动关闭，注意单位是毫秒（1秒=1000毫秒）                                                          |
| id         | ''                   | 用于控制弹层唯一标识   | 设置该值后，不管是什么类型的层，都只允许同时弹出一个。一般用于页面层和iframe层模式                                                                          |
| anim       | 0                    | 弹出动画         | 目前anim可支持的动画类型有0-6 如果不想显示动画，设置 anim: -1 即可。（0平滑放大）（1从上掉落） （2从最底部往上滑入）（3从左滑入）（4从左翻滚） （5渐显）（6抖动）                        |
| isOutAnim  | true                 | 关闭动画         | 默认情况下，关闭层时会有一个过度动画。如果你不想开启，设置 isOutAnim: false 即可                                                                     |
| maxmin     | false                | 最大最小化        | 该参数值对type:1和type:2有效。默认不显示最大小化按钮。需要显示配置maxmin: true即可                                                                 |
| fixed      | true                 | 固定           | 即鼠标滚动时，层是否固定在可视区域。如果不想，设置fixed: false即可                                                                               |
| resize     | true                 | 是否允许拉伸       | 默认情况下，你可以在弹层右下角拖动来拉伸尺寸。如果对指定的弹层屏蔽该功能，设置 false即可。该参数对loading、tips层无效                                                   |
| resizing   | null                 | 监听窗口拉伸动作     | 当你拖拽弹层右下角对窗体进行尺寸调整时，如果你设定了该回调，则会执行。回调返回一个参数：当前层的DOM对象                                                                 |
| scrollbar  | true                 | 是否允许浏览器出现滚动条 | 默认允许浏览器滚动，如果设定scrollbar: false，则屏蔽                                                                                    |
| maxWidth   | 360                  | 最大宽度         | 请注意：只有当area: 'auto'时，maxWidth的设定才有效。                                                                                  |
| maxHeight  | 无                    | 最大高度         | 请注意：只有当高度自适应时，maxHeight的设定才有效。                                                                                        |
| zIndex     | 19891014             | 层叠顺序         | 一般用于解决和其它组件的层叠冲突。                                                                                                     |
| move       | '.layui-layer-title' | 触发拖动的元素      | 默认是触发标题区域拖拽。如果你想单独定义，指向元素的选择器或者DOM即可。如move: '.mine-move'。你还配置设定move: false来禁止拖拽                                       |
| moveOut    | false                | 是否允许拖拽到窗口外   | 默认只能在窗口内拖拽，如果你想让拖到窗外，那么设定moveOut: true即可                                                                              |
| moveEnd    | null                 | 拖动完毕后的回调方法   | 默认不会触发moveEnd，如果你需要，设定moveEnd: function(layero){}即可。其中layero为当前层的DOM对象                                                |
| tips       | 2                    | 方向和颜色        | tips层的私有参数。支持上右下左四个方向，通过1-4进行方向设定。如tips: 3则表示在元素的下面出现。有时你还可能会定义一些颜色，可以设定tips: [1, '#c00']                             |
| tipsMore   | false                | 是否允许多个tips   | 允许多个意味着不会销毁之前的tips层。通过tipsMore: true开启                                                                                |
| success    | null                 | 层弹出后的成功回调方法  | 当你需要在层创建完毕时即执行一些语句，可以通过该回调。success会携带两个参数，分别是当前层DOM当前层索引。                                                             |
| yes        | null                 | 确定按钮回调方法     | 该回调携带两个参数，分别为当前层索引、当前层DOM对象。                                                                                          |
| cancel     | null                 | 右上角关闭按钮触发的回调 | 该回调携带两个参数，分别为：当前层索引参数（index）、当前层的DOM对象（layero），默认会自动触发关闭。如果不想关闭，return false即可                                        |
| end        | null                 | 层销毁后触发的回调    | 无论是确认还是取消，只要层被销毁了，end都会执行，不携带任何参数。                                                                                    |
| full       | null                 | 最大化          | 最大化触发的回调                                                                                                              |
| min        | null                 | 最小化          | 最小化触发的回调                                                                                                              |
| restore    | null                 | 还原后          | 还原后触发的回调                                                                                                              |

内置方法。

| 名称                                           | 描述             | 备注                                                                                                                 |
| -------------------------------------------- | -------------- | ------------------------------------------------------------------------------------------------------------------ |
| layer.ready(callback)                        | 初始化就绪          | 由于我们的layer内置了轻量级加载器，所以你根本不需要单独引入css等文件。但是加载总是需要过程的。当你在页面一打开就要执行弹层时，你最好是将弹层放入ready方法中                               |
| layer.open(options)                          | 原始核心方法         | 基本上是露脸率最高的方法，不管是使用哪种方式创建层，都是走layer.open()，创建任何类型的弹层都会返回一个当前层索引，上述的options即是基础参数                                    |
| layer.alert(content, options, yes)           | 普通信息框          | 它的弹出似乎显得有些高调，一般用于对用户造成比较强烈的关注，类似系统alert，但却比alert更灵便。它的参数是自动向左补齐的。通过第二个参数，可以设定各种你所需要的基础参数，但如果你不需要的话，直接写回调即可。        |
| layer.confirm(content, options, yes, cancel) | 询问框            | 请求远程校验。url 类似系统confirm，但却远胜confirm，另外它不是和系统的confirm一样阻塞你需要把交互的语句放在回调体中。同样的，它的参数也是自动补齐的。                            |
| layer.msg(content, options, end)             | 提示框            | 消息提示                                                                                                               |
| layer.load(icon, options)                    | 加载层            | type:3的深度定制。load并不需要你传太多的参数，但如果你不喜欢默认的加载风格，你还有选择空间。icon支持传入0-2如果是0，无需传。另外特别注意一点：load默认是不会自动关闭的，因为你一般会在ajax回调体中关闭它。 |
| layer.tips(content, follow, options)         | tips层          | type:4的深度定制。也是我本人比较喜欢的一个层类型，因为它拥有和msg一样的低调和自觉，而且会智能定位，即灵活地判断它应该出现在哪边。默认是在元素右边弹出                                    |
| layer.close(index)                           | 关闭特定层          | 关于它似乎没有太多介绍的必要，唯一让你疑惑的，可能就是这个index了吧。事实上它非常容易得到。                                                                   |
| layer.closeAll(type)                         | 关闭所有层          | 如果你很懒，你不想去获取index你只想关闭。那么closeAll真的可以帮上你。如果你不指向层类型的话，它会销毁掉当前页所有的layer层。                                            |
| layer.style(index, cssStyle)                 | 重新定义层的样式       | 该方法对loading层和tips层无效。参数index为层的索引，cssStyle允许你传入任意的css属性                                                            |
| layer.title(title, index)                    | 改变层的标题         | 使用方式：layer.title('标题变了', index)                                                                                    |
| layer.getChildFrame(selector, index)         | 获取iframe页的DOM  | 当你试图在当前页获取iframe页的DOM元素时，你可以用此方法。selector即iframe页的选择器                                                              |
| layer.getFrameIndex(windowName)              | 获取特定iframe层的索引 | 此方法一般用于在iframe页关闭自身时用到。                                                                                            |
| layer.iframeAuto(index)                      | 指定iframe层自适应   | 调用该方法时，iframe层的高度会重新进行适应                                                                                           |
| layer.iframeSrc(index, url)                  | 重置特定iframe url | 似乎不怎么常用的样子。使用方式：layer.iframeSrc(index, 'http://ruoyi.vip')                                                         |
| layer.setTop(layero)                         | 置顶当前窗口         | 非常强大的一个方法，虽然一般很少用。但是当你的页面有很多很多layer窗口，你需要像Window窗体那样，点击某个窗口，该窗体就置顶在上面，那么setTop可以来轻松实现。它采用巧妙的逻辑，以使这种置顶的性能达到最优       |
| layer.full()                                 | 最大化            | 一般用于在自定义元素上触发最大化。                                                                                                  |
| layer.min()                                  | 最小化            | 一般用于在自定义元素上触发最大小。                                                                                                  |
| layer.restore()                              | 还原后            | 一般用于在自定义元素上触发还原后。                                                                                                  |
| layer.prompt(options, yes)                   | 输入层            | prompt的参数也是向前补齐的。options不仅可支持传入基础参数，还可以传入prompt专用的属性。当然，也可以不传。yes携带value 表单值index 索引elem 表单元素                      |
| layer.tab(options)                           | tab层           | tab层只单独定制了一个成员，即tab: []，                                                                                           |
| layer.photos(options)                        | 相册层            | 相册层，也可以称之为图片查看器。它的出场动画从layer内置的动画类型中随机展现。photos支持传入json和直接读取页面图片两种方式。                                              |
