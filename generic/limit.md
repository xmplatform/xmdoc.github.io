项目中所有的注解在 com.fun.framework 包下，`@Limit`注解可以实现接口的限流，该注解与本文转自[FEBS](https://shiro.mrbird.cc)，这个注解很不错（择其优而用），在项目中对该注解调整后也整合进来了。规定一段时间内最多可以访问该接口的次数，超过这个次数则拒绝访问。关于此注解的原理：依赖的是 redis 和 lua 脚本，redis 是可以执行lua 脚本的，在用户访问接口的时候，执行一次这个脚本即可。

`@Limit`注解如下所示：

```java
import com.fun.framework.annotation.enums.LimitType;

@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface Limit {

    /**  资源名称，用于描述接口功能 */
    String name() default "";

    /** 资源 key */
    String key() default "";

    /** key prefix */
    String prefix() default "";

    /** 时间范围，单位秒 */
    int period();

    /** 限制访问次数 */
    int count();

    /** 限制类型 */
    LimitType limitType() default LimitType.CUSTOMER;
}
```

其中，`limitType`包含传统类型限流和根据IP限流，其为枚举类型：

```java
public enum LimitType {
    /**  传统类型
     */
    CUSTOMER,
    /** 根据 IP 地址限制
     */
    IP
}
```

**使用示例**

```java
@RestController
public class TestController {

    private static final AtomicInteger ATOMIC_INTEGER = new AtomicInteger();

    @Limit(key = "test", period = 600, count = 10, name = "resource", prefix = "limit")
    @GetMapping("/test")
    public int testLimiter() {
        return ATOMIC_INTEGER.incrementAndGet();
    }
}
```

`@Limit(key = "test", period = 600, count = 10, name = "resource", prefix = "limit")` 的意思是在600秒内最多只能访问10次，当600秒内第11次访问该接口时，接口返回`{"code":500,"msg":"系统繁忙，请稍后再试"}`。
