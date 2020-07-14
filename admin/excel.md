项目中提供了两个注解 @Excel 和 @Excels。主要依赖的apache提供的 `poi`。

### Maven poi

```xml
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi-ooxml</artifactId>
    <version>3.17</version>
</dependency>
```

### `@Excel`注解

对于很多的属性我们直接转成中文导出，肯定是满足不了大多数要求的，况且很多格式都是很不友好的，所以如下，合适的使用以下注解属性，可以解决很多的问题，为你节约大量的时间。

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.FIELD)
public @interface Excel {
    /** 导出到Excel中的名字.  */
    String name() default "" ;

    /** 日期格式, 如: yyyy-MM-dd */
    String dateFormat() default "" ;

    /** 读取内容转表达式 (如: 0=男,1=女,2=未知) */
    String readConverterExp() default "" ;

    /** 导出类型（0数字 1字符串） */
    ColumnType cellType() default ColumnType.STRING;

    /** 导出时在excel中每个列的高度 单位为字符 */
    double height() default 14;

    /** 导出时在excel中每个列的宽 单位为字符 */
    double width() default 16;

    /** 文字后缀,如% 90 变成90% */
    String suffix() default "" ;

    /** 当值为空时,字段的默认值 */
    String defaultValue() default "" ;

    /** 提示信息 */
    String prompt() default "" ;

    /** 设置只能选择不能输入的列内容. */
    String[] combo() default {};

    /** 是否导出数据,应对需求:有时我们需要导出一份模板,这是标题需要但内容需要用户手工填写. */
    boolean isExport() default true;

    /** 另一个类中的属性名称,支持多级获取,以小数点隔开 */
    String targetAttr() default "" ;

    /** 字段类型（0：导出导入；1：仅导出；2：仅导入） */
    Type type() default Type.ALL;
}
```

该注解加到需要导出的实体类中的属性上，使用示例如下：

```java
public class AdminUser extends BaseEntity {
    @Excel(name = "用户序号", cellType = ColumnType.NUMERIC, prompt = "用户编号")
    private Long userId;

    @Excel(name = "部门编号", type = Type.IMPORT)
    private Long deptId;

    @Excel(name = "登录账号")
    private String loginName;

    @Excel(name = "用户性别", readConverterExp = "0=男,1=女,2=未知")
    private String sex;
}
```

### `@Excels`注解

```java
@Target(ElementType.FIELD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Excels {
    Excel[] value();
}
```

该注解主要使用的场景为当前实体类中的属性为另一个实体类的对象。如下：

```java
public class AdminUser extends BaseEntity {
/**
     * 部门对象
     */
    @Excels({
            @Excel(name = "部门名称", targetAttr = "deptName", type = Type.EXPORT),
            @Excel(name = "部门负责人", targetAttr = "leader", type = Type.EXPORT)
    })
    private Dept dept;
}
```

这样即可和当前的实体类的对象和对象的属性一同导出。

### Excel导入

导入数据时，需要当前的 excel 模板符合模板格式。


