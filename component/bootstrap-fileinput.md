bootstrap-fileinput.js是一款文件上传插件

代码演示参考 FUN-BOOT系统 → 实例演示 → 表单元素 → 文件上传 `form/upload.html`（项目使用需要引入css和js）

1、<th:block th:include="include :: bootstrap-fileinput-css" />  
2、<th:block th:include="include :: bootstrap-fileinput-js" />

| 属性                       | 类型           | 默认值                                                                                                                                                                                         | 描述                                                                                                                            |
| ------------------------ | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| language                 | String       | 'en'                                                                                                                                                                                        | 多语言设置，使用时需提前引入locales文件夹下对应的语言文件，中文zh，引入语言文件必须放在fileinput.js之后                                                                |
| showCaption              | Boolean      | true                                                                                                                                                                                        | 是否显示被选文件的简介                                                                                                                   |
| showBrowse               | Boolean      | true                                                                                                                                                                                        | 是否显示浏览按钮                                                                                                                      |
| showPreview              | Boolean      | true                                                                                                                                                                                        | 是否显示预览区域                                                                                                                      |
| showRemove               | Boolean      | true                                                                                                                                                                                        | 是否显示移除按钮                                                                                                                      |
| showUpload               | Boolean      | true                                                                                                                                                                                        | 是否显示上传按钮                                                                                                                      |
| showCancel               | Boolean      | true                                                                                                                                                                                        | 是否显示取消按钮                                                                                                                      |
| showClose                | Boolean      | true                                                                                                                                                                                        | 是否显示关闭按钮                                                                                                                      |
| showUploadedThumbs       | Boolean      | true                                                                                                                                                                                        | 这个属性是基于这样一个使用方法的：选择若干个文件后点击右下角上传按钮批量上传，待全部完成后再选择一批文件，此时之前上传成功的文件是否要保存。就是这个属性控制的。注意，点击文件缩略图下面的上传按钮不会导致之前的成功上传的文件消失，即使这里设置了true |
| browseOnZoneClick        | Boolean      | false                                                                                                                                                                                       |                                                                                                                               |
| autoReplace              | Boolean      | false                                                                                                                                                                                       | 是否自动替换当前图片，设置为true时，再次选择文件， 会将当前的文件替换掉。                                                                                       |
| generateFileId           | Object       | null                                                                                                                                                                                        |                                                                                                                               |
| previewClass             | String       | 空                                                                                                                                                                                           | 添加预览按钮的类属性                                                                                                                    |
| captionClass             | String       | 空                                                                                                                                                                                           | 添加标题类属性                                                                                                                       |
| frameClass               | String       | 'krajee-default'                                                                                                                                                                            | 针对每个缩略图的框架                                                                                                                    |
| mainClass                | String       | 'file-caption-main'                                                                                                                                                                         | 针对元素类属性                                                                                                                       |
| mainTemplate             | Object       | null                                                                                                                                                                                        |                                                                                                                               |
| purifyHtml               | Boolean      | true                                                                                                                                                                                        |                                                                                                                               |
| fileSizeGetter           | Object       | null                                                                                                                                                                                        |                                                                                                                               |
| initialCaption           | String       | 空                                                                                                                                                                                           |                                                                                                                               |
| initialPreview           | Array/Object | []                                                                                                                                                                                          | 通过这个参数，我们可以为文件区设置一些默认的缩略图                                                                                                     |
| initialPreviewDelimiter  | String       | '$$'                                                                                                                                                                                        |                                                                                                                               |
| initialPreviewAsData     | Boolean      | false                                                                                                                                                                                       |                                                                                                                               |
| initialPreviewFileType   | String       | 'image'                                                                                                                                                                                     |                                                                                                                               |
| initialPreviewConfig     | Array/Object | []                                                                                                                                                                                          |                                                                                                                               |
| initialPreviewThumbTags  | Array/Object | []                                                                                                                                                                                          |                                                                                                                               |
| previewThumbTags         | Object       | {}                                                                                                                                                                                          |                                                                                                                               |
| initialPreviewShowDelete | Boolean      | true                                                                                                                                                                                        |                                                                                                                               |
| removeFromPreviewOnError | Boolean      | false                                                                                                                                                                                       |                                                                                                                               |
| deleteUrl                | String       | 空                                                                                                                                                                                           | 删除图片时的请求路径                                                                                                                    |
| deleteExtraData          | Object       | {}                                                                                                                                                                                          | 删除图片时额外传入的参数                                                                                                                  |
| overwriteInitial         | Boolean      | true                                                                                                                                                                                        |                                                                                                                               |
| previewZoomButtonIcons   | Object       | {prev: '',next: '',toggleheader: '',fullscreen: '',borderless: '',close: ''},                                                                                                               |                                                                                                                               |
| previewZoomButtonClasses | Object       | {prev: 'btn btn-navigate',next: 'btn btn-navigate',toggleheader: 'btn btn-default btn-header-toggle',fullscreen: 'btn btn-default',borderless: 'btn btn-default',close: 'btn btn-default'}, |                                                                                                                               |
| preferIconicPreview      | Boolean      | false                                                                                                                                                                                       |                                                                                                                               |
| preferIconicZoomPreview  | Boolean      | false                                                                                                                                                                                       |                                                                                                                               |
| allowedPreviewTypes      | undefined    | undefined                                                                                                                                                                                   |                                                                                                                               |
| allowedPreviewMimeTypes  | Object       | null                                                                                                                                                                                        |                                                                                                                               |
| allowedFileTypes         | Object       | null                                                                                                                                                                                        | 接收的文件后缀，如['jpg', 'gif', 'png'],不填将不限制上传文件后缀类型                                                                                 |
| allowedFileExtensions    | Object       | null                                                                                                                                                                                        | 指出带有哪些后缀名的文件才是被接受上传的，设置msgInvalidFileExtension可以个性化出现此错误时的错误信息                                                                |
| defaultPreviewContent    | Object       | null                                                                                                                                                                                        |                                                                                                                               |
| customLayoutTags         | Object       | {}                                                                                                                                                                                          |                                                                                                                               |
| customPreviewTags        | Object       | {}                                                                                                                                                                                          |                                                                                                                               |
| previewFileIcon          | String       | 空                                                                                                                                                                                           | 当文件无法被预览时出现在缩略图中的图标，默认是                                                                                                       |
| previewFileIconClass     | String       | 'file-other-icon'                                                                                                                                                                           |                                                                                                                               |
| previewFileIconSettings  | Object       | {}                                                                                                                                                                                          | 可以将不同的后缀的文件有不同的缩略图图标                                                                                                          |
| previewFileExtSettings   | Object       | {}                                                                                                                                                                                          |                                                                                                                               |
| buttonLabelClass         | String       | 'hidden-xs'                                                                                                                                                                                 |                                                                                                                               |
| browseIcon               | String       | 空                                                                                                                                                                                           |                                                                                                                               |
| browseClass              | String       | 'btn btn-primary'                                                                                                                                                                           | 指出了右下角选择按钮的样式。一般尽量不要用btn-sm和btn-lg，会和左边的输入框不协调                                                                                |
| removeIcon               | String       | 空                                                                                                                                                                                           | 删除按钮相关的属性                                                                                                                     |
| removeClass              | String       | 'btn btn-default'                                                                                                                                                                           |                                                                                                                               |
| cancelIcon               | String       | 空                                                                                                                                                                                           |                                                                                                                               |
| cancelClass              | String       | 'btn btn-default'                                                                                                                                                                           |                                                                                                                               |
| uploadIcon               | String       | 空                                                                                                                                                                                           | 上传按钮相关的属性                                                                                                                     |
| uploadClass              | String       | 'btn btn-default'                                                                                                                                                                           |                                                                                                                               |
| uploadUrl                | String       | null                                                                                                                                                                                        | 上传文件路径                                                                                                                        |
| uploadAsync              | boolean      | true                                                                                                                                                                                        | 是否为异步上传                                                                                                                       |
| uploadExtraData          | Object       | {}                                                                                                                                                                                          | 上传文件时额外传递的参数设置                                                                                                                |
| zoomModalHeight          | number       | 480                                                                                                                                                                                         |                                                                                                                               |
| minImageWidth            | String       | null                                                                                                                                                                                        | 图片的最小宽度                                                                                                                       |
| minImageHeight           | String       | null                                                                                                                                                                                        | 图片的最小高度                                                                                                                       |
| maxImageWidth            | String       | null                                                                                                                                                                                        | 图片的最大宽度                                                                                                                       |
| maxImageHeight           | String       | null                                                                                                                                                                                        | 图片的最大高度                                                                                                                       |
| resizeImage              | Boolean      | false                                                                                                                                                                                       |                                                                                                                               |
| resizePreference         | String       | 'width'                                                                                                                                                                                     |                                                                                                                               |
| resizeQuality            | number       | 0.92                                                                                                                                                                                        |                                                                                                                               |
| resizeDefaultImageType   | String       | 'image/jpeg'                                                                                                                                                                                |                                                                                                                               |
| minFileSize              | number       | 0                                                                                                                                                                                           | 单位为kb，上传文件的最小大小值                                                                                                              |
| maxFileSize              | number       | 0                                                                                                                                                                                           | 单位为kb，如果为0表示不限制文件大小                                                                                                           |
| resizeDefaultImageType   | number       | 25600(25MB)                                                                                                                                                                                 |                                                                                                                               |
| minFileCount             | number       | 0                                                                                                                                                                                           | 表示同时最小上传的文件个数                                                                                                                 |
| maxFileCount             | number       | 0                                                                                                                                                                                           | 表示允许同时上传的最大文件个数                                                                                                               |
| validateInitialCount     | Boolean      | false                                                                                                                                                                                       |                                                                                                                               |
| msgValidationErrorClass  | String       | 'text-danger'                                                                                                                                                                               |                                                                                                                               |
| msgValidationErrorIcon   | String       | 空                                                                                                                                                                                           |                                                                                                                               |
| msgErrorClass            | String       | 'file-error-message'                                                                                                                                                                        |                                                                                                                               |
| progressThumbClass       | String       | "progress-bar progress-bar-success progress-bar-striped active"                                                                                                                             |                                                                                                                               |
| rogressClass             | String       | "progress-bar progress-bar-success progress-bar-striped active"                                                                                                                             |                                                                                                                               |
| progressCompleteClass    | String       | "progress-bar progress-bar-success"                                                                                                                                                         |                                                                                                                               |
| progressErrorClass       | String       | "progress-bar progress-bar-danger"                                                                                                                                                          |                                                                                                                               |
| progressUploadThreshold  | number       | 99                                                                                                                                                                                          |                                                                                                                               |
| previewFileType          | String       | 'image'                                                                                                                                                                                     | 预览文件类型,内置['image', 'html', 'text', 'video', 'audio', 'flash', 'object',‘other‘]等格式                                            |
| elCaptionContainer       | String       | null                                                                                                                                                                                        |                                                                                                                               |
| elCaptionText            | String       | null                                                                                                                                                                                        | 设置标题栏提示信息                                                                                                                     |
| elPreviewContainer       | String       | null                                                                                                                                                                                        |                                                                                                                               |
| elPreviewImage           | String       | null                                                                                                                                                                                        |                                                                                                                               |
| elPreviewStatus          | String       | null                                                                                                                                                                                        |                                                                                                                               |
| elErrorContainer         | String       | null                                                                                                                                                                                        |                                                                                                                               |
| errorCloseButton         | String       | ×'                                                                                                                                                                                          |                                                                                                                               |
| slugCallback             | function     | null                                                                                                                                                                                        | 选择后未上传前 回调方法                                                                                                                  |
| dropZoneEnabled          | Boolean      | true                                                                                                                                                                                        | 是否显示拖拽区域                                                                                                                      |
| dropZoneTitleClass       | String       | 'file-drop-zone-title'                                                                                                                                                                      | 拖拽区域类属性设置                                                                                                                     |
| fileActionSettings       | Object       | {}                                                                                                                                                                                          | 设置预览图片的显示样式                                                                                                                   |
| otherActionButtons       | String       | 空                                                                                                                                                                                           | 编码设置                                                                                                                          |
| textEncoding             | String       | 'UTF-8'                                                                                                                                                                                     |                                                                                                                               |
| ajaxSettings             | Object       | {}                                                                                                                                                                                          |                                                                                                                               |
| ajaxDeleteSettings       | Object       | {}                                                                                                                                                                                          |                                                                                                                               |
| showAjaxErrorDetails     | Boolean      | true                                                                                                                                                                                        |                                                                                                                               |

Method说明。

| 方法名                    | 描述                                                                                          |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| fileerror              | 异步上传错误结果处理$('#uploadfile').on('fileerror', function(event, data, msg) {});                  |
| fileuploaded           | 异步上传成功结果处理$("#uploadfile").on("fileuploaded", function (event, data, previewId, index) {})  |
| filebatchuploaderror   | 批量上传错误结果处理$('#uploadfile').on('filebatchuploaderror', function(event, data, msg) {});       |
| filebatchuploadsuccess | 批量上传成功结果处理$('#uploadfile').on('filepreupload', function(event, data, previewId, index) {}); |
| filebatchselected      | 选择文件后处理事件$("#fileinput").on("filebatchselected", function(event, files) {});                |
| upload                 | 文件上传方法$("#fileinput").fileinput("upload");                                                  |
| fileuploaded           | 上传成功后处理方法$("#fileinput").on("fileuploaded", function(event, data, previewId, index) {});    |
| filereset              | Possible values: http, https, ws, wss.                                                      |
| fileclear              | 点击浏览框右上角X 清空文件前响应事件$("#fileinput").on("fileclear",function(event, data, msg){});            |
| filecleared            | 点击浏览框右上角X 清空文件后响应事件$("#fileinput").on("filecleared",function(event, data, msg){});          |
| fileimageuploaded      | 在预览框中图片已经完全加载完毕后回调的事件                                                                       |