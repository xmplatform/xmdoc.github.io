# 配置文件

在整个脚手架的项目中，有 application.yml 、application-dev.yml、application-prod.yml、application-test.yml、fun-boot.properties 五个配置文件。prod的配置对数据库的账号密码进行了加密，具体加密方法见文档。fun-boot.properties是整个项目中自定义的一些配置项。

> 在 FUN-BOOT 快速迭代时期，不保证配置文件向后兼容。在您修改配置文件之前，务必弄懂含义，并做好备份。

## 项目配置

基本上每一个配置项都有注释信息，这里不再过多赘述。APP端的RSA加密默认关闭。如果需要使用该加密算法，生成密匙对见 utils 中的 encrypt.RsaUtils.java 工具类。

```yaml
#---------------------- 项目相关配置 ----------------
# 名称
fun.name=FunBoot
# 版本
fun.version=1.0.0
# 版权年份
fun.copyrightYear=2019
# 实例演示开关
fun.demoEnabled=false
# 文件路径 示例（ Windows配置D:/fun/uploadPath，Linux配置 /home/fun/uploadPath）
fun.profile=D:/fun/uploadPath
# 日志开关，开启后将日志异步记录在数据库
fun.openLog=false

#------------------ 代码生成工具配置 ----------------
# 作者
gen.author=DJun
# 默认生成包路径 system 需改成自己的模块名称 如 system monitor tool
gen.packageName=com.fun.project.admin.system
# 自动去除表前缀，默认是true
autoRemovePre=true
# 表前缀(类名不会包含表前缀)
tablePrefix=sys_

#---------------------- XSS过滤 --------------------
xss.enabled=true
xss.excludes=/admin/system/notice/*
xss.urlPatterns=/app/*,/admin/*

#---------------------- Shiro 配置 -----------------
# 登录地址
shiro.loginUrl=/admin/login
# 权限认证失败地址
shiro.unauthorizedUrl=/403
# 首页地址
shiro.indexUrl=/admin/index
# 验证码拦截开关
shiro.captchaEnabled=true
# 验证码类型 math 数组计算 char 字符
shiro.captchaType=math
# Session 过期时间（秒）
shiro.sessionTimeout=3600
# 记住登录(秒，默认一天)
shiro.cookieTimeout=86400
# 免认证URI
shiro.anonUrl=/app/**,/main/**,/img/**,/fun/**,/captcha/captchaImage**,/admin/login/**
# 退出登录地址
shiro.logoutUrl=/admin/logout

#---------------------- APP 配置 ------------------
# 公钥
rsa.publicKey=MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAIMQdC5BcuQaK0GOzWhTxaNkksXMm6vWtpBQ_nFlU1wPIGeU0s9X4mWvqQHFvyACXIJaCCWZxTvsXnfNW12jTm8CAwEAAQ
# 私钥
rsa.privateKey=MIIBVAIBADANBgkqhkiG9w0BAQEFAASCAT4wggE6AgEAAkEAgxB0LkFy5BorQY7NaFPFo2SSxcybq9a2kFD-cWVTXA8gZ5TSz1fiZa-pAcW_IAJcgloIJZnFO-xed81bXaNObwIDAQABAkAjFl-UFo90g5D6_wj8mhi6Em28qHcwfM3pOtWzc-XqKfqgnh9bZ18tBiwiIkJRw3P-i2FrM4KiKe0ZfAzbDpSpAiEA3jGRgUrSyPhPPLc98ztVgK77fBAEjAjEdtEl-IlE3jMCIQCXAWa6RhL9JN5e5F9uVcnTUbF0P6ZiioEcWQ5zyGXa1QIgDGwZBnF4d2Pqiip0fDTFAvzFcpoypuGWmk33IX4LK6ECIQCMJ8TNR5UAWGP890KMChwVg1GNcDZiZ-OGCDKdzHadMQIgRJCG5NpeX4myojOeFgCFGEp4ace2NW8vnLBkElz8ego
# 签名
rsa.signature=fun-boot
# JWT的超期限时间(默认一天，单位ms)
jwt.expiration=3600000
# 记住我token过期时间(默认七天，单位ms)
jwt.expirationRemember=604800000
# 存入Redis的头
jwt.userPrefix=token_

```

## 其它配置

Druid 和 Swagger 的配置等，在 framework -> config 目录找到配置文件。如果我当前一个主库和一个从库不能满足您的需求，你可以在 datasource 修改配置代码。


