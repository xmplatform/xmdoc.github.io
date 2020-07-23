随着子项目日渐增多，版本号一个个子模块修改非常麻烦，可使用插件versions-maven-plugin解决。

**使用方式**
在主项目的pom中放入如下插件：

```html
<plugin>
    <groupId>org.codehaus.mojo</groupId>
    <artifactId>versions-maven-plugin</artifactId>
    <version>2.7</version>
    <configuration>
        <generateBackupPoms>false</generateBackupPoms>
        <processAllModules>true</processAllModules>
        <newVersion>1.0.5</newVersion>
    </configuration>
</plugin>
```

configuration含义如下：


```javascript
I18n.t("xxx"); //其中xxx表示国际化的key，例如I18n.t("立即登录")
```

3、java上的使用：

```java
I18nUtils.t("xxx"); //其中xxx表示国际化的key，例如I18nUtils.t("立即登录");
```
