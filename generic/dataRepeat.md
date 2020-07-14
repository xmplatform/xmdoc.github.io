有的时候，在项目中可能会出现表单数据重复提交的问题，这样的情况比如会因为一些接口后台是不需要对提交到的数据做校验。故在本脚手架中，考虑到这样的情况，也提供了一个防重复提交的注解。

**使用方式**

将此注解加到需要防重复提交的方法上使用。

```java
@Inherited
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
@Documented
public @interface RepeatSubmit {}
```

**注解的实现**

该注解是通过判断同一请求体在一定的时间内（在项目中默认为2秒），提交的多次提交的参数是否完全相同，若相同则判定为重复提交。此注解是通过继承拦截器`HandlerInterceptorAdapter` 来实现的，具体代码在`com.fun.framework.interceptor`中。

**修改拦截URI**

当然，拦截器拦截的路径也是可以修改的，默认是全局都会检查是否存在`@RepeatSubmit` 。如果需要修改拦截位置，修改`com.fun.framework.interceptor.InterceptorConfig`的

`registry.addInterceptor(repeatSubmitInterceptor).addPathPatterns("/**");`即可。
