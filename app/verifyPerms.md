关于权限部分，值得一提的是，在整个项目中，对超级管理员这个身份是不需要进行权限验证的，一路畅通。从一定意义上来说，节省了性能。

在本项目的App的脚手架设计中，一个用户只能具备一个角色，可以分配给这个角色相应的权限。

### 校验

通过自定义注解`@JwtPermission`来实现权限校验。

```java
@Target(ElementType.METHOD)
@Retention(RetentionPolicy.RUNTIME)
public @interface JwtPermission {
    String value() default "";
}
```

当App接口需要验证权限时，将该注解应用于Controller的方法上，如`@JwtPermission("user:view")`，表示当前用户的角色需要具备`user:view`才可访问该接口。

### FUN-BOOT是如何实现`@JwtPermission`注解？

当用户在登录成功的时候，就会把当前用户的个人信息存放到缓存中去。需要的权限验证，也会去缓存中获取当前登录用户的个人信息，主要获取当前用户的角色，再到数据库中去查询当前角色的全部权限（超级管理员除外）。
