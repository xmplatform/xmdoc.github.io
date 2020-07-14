在项目中，为了给大家提供一个快速开发、简单开发的环境，特整合了多数据源的配置。一来，节省你的开发时间；二来，作为多数据源配置示例，若不能满足您的需求，可以作为参考修改。

若在你的项目中，有多数据源的这个需求，请继续往下阅读：

在项目中，默认是关闭了从库这个功能的，所以需要将 application-prod.yml 中slave的enabled属性设为True：

```yaml
spring:
  datasource:
    ...
    druid:
      master:
       ...
      slave:
        enabled: false
        url: jdbc:mysql://localhost:3306/fun_slave?useUnicode=true&characterEncoding=utf8&zeroDateTimeBehavior=convertToNull&useSSL=true&serverTimezone=GMT%2B8

        username: ENC(QJfMvdDbMiVQc8OqewSUQw==)
        password: ENC(2+pgvPF9DJQx9fOIlH5hvA==)
```

### `@DataSource`注解

在本项目中是通过将此注解运用在方法上实现切换数据源的，但请注意，在该方法调用完成后会销毁当前数据源，也就是清空当前数据源的变量。

```java
@Target({ElementType.METHOD, ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Inherited
public @interface DataSource {
    /**  切换数据源名称 */
    DataSourceType value() default DataSourceType.MASTER;
}
```

关于数据源部分，做成了一个枚举，如果你还需要其它的数据源，在此新增，修改 framework -> datasource 的代码即可。

```java
public enum DataSourceType {
    /**  主库 */
    MASTER,
    /**  从库 */
    SLAVE
}
```

在Service层或Controller层使用，示例如下：

```java
    @DataSource(DataSourceType.SLAVE)

    @PostMapping("/list")
    @ResponseBody
    public CommonResult<CommonPage<OperLog>> operList(OperLog operLog) {
        startPage();
        List<OperLog> list = operLogService.selectOperLogList(operLog);
        return success(CommonPage.restPage(list));
    }
```

当调用这个方法的时候，数据源配置成功，在控制台输出的日志可以看到：

```
2019-12-05 17:18:47 | INFO  | http-nio-8886-exec-1 | com.fun.framework.dasource.DynamicDataSourceContextHolder | 切换到SLAVE数据源
2019-12-05 17:18:47 | INFO  | http-nio-8886-exec-1 | com.alibaba.druid.pool.DruidDataSource | {dataSource-2} inited
```

到这里，使用基本上就ok了。那么项目中是如何来做到数据源切换的呢？

**获取配置信息**

在Druid的配置代码 com.fun.framework.datasouce.DruidConfig 中，有以下两个Bean来获取 yaml 配置文件中配置的参数：

```java
    @Bean

    @ConfigurationProperties("spring.datasource.druid.master")
    public DataSource masterDataSource(DruidProperties druidProperties) {
        DruidDataSource dataSource = DruidDataSourceBuilder.create().build();
        return druidProperties.dataSource(dataSource);
    }

    @Bean
    @ConfigurationProperties("spring.datasource.druid.slave")
    @ConditionalOnProperty(prefix = "spring.datasource.druid.slave", name = "enabled", havingValue = "true")
    public DataSource slaveDataSource(DruidProperties druidProperties) {
        DruidDataSource dataSource = DruidDataSourceBuilder.create().build();
        return druidProperties.dataSource(dataSource);
    }
```

**切换数据源**

项目中是通过 ThreadLocal 来维护数据源变量的，ThreadLocal为每个使用该变量的线程提供独立的变量副本，所以每一个线程都可以独立地改变自己的副本，而不会影响其它线程所对应的副本。

通过一个类来继承JDBC的AbstractRoutingDataSource 实现determineCurrentLookupKey()方法，将当前数据源变量返回。


