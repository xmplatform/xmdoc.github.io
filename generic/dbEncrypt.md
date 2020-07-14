在 application.yml 中，数据库的账号和密码使用明文可能会不太安全，可以使用 jasypt 来加密。

Maven jasypt 依赖：

```xml
<dependency>
    <groupId>com.github.ulisesbocchio</groupId>
    <artifactId>jasypt-spring-boot-starter</artifactId>
    <version>2.1.0</version>
</dependency>
```

在项目配置文件application.yml中配置用于加密的密钥：

```yaml
jasypt:
  encryptor:
    password: fun-boot
```

然后写个测试方法来生成加密之后的账号和密码，如我当前数据库的账号和密码都为root：

```java
@Test
    public void test() {
        BasicTextEncryptor encryptor = new BasicTextEncryptor();
        encryptor.setPassword("fun-boot");
        String encryptedDatasourceUsername = encryptor.encrypt("root");
        String encryptedDatasourcePassword = encryptor.encrypt("root");
        System.out.println("用户名加密结果：" + encryptedDatasourceUsername);
        System.out.println("密码加密结果：" + encryptedDatasourcePassword);

    }
```

运行该方法，获取到加密之后的账号密码：

> 用户名加密结果：cmPWzYFwbJDxBhHyjV5Uiw==
> 
> 
> 密码加密结果：E9cC9ckyFzMvvSF4UMy6Vw==

把生成的密文加上ENC()作为数据库的账号和密码，如下所示：

```yaml
spring:
  datasource: 
    druid:
     ...
        username: ENC(cmPWzYFwbJDxBhHyjV5Uiw==)
        password: ENC(E9cC9ckyFzMvvSF4UMy6Vw==)
```

可参考项目中的 application-prod.yml。
