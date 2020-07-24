**yml配置项中的命名不能使用驼峰**

@ConfigurationProperties配置的限制

SpringBoot 中可以使用 @ConfigurationProperties 将一个实体类转变为可配置的类（在properties文件中可以直接配置对应参数的值，如果使用IDE的话，会自动提示）。在 SpringBoot 1.5.9 中设置 @ConfigurationProperties 的 prefix 属性时，使用驼峰命名(如eclipseLink)不会有任何问题，但在 Spring Boot 2.x 启动时会报错：

InvalidConfigurationPropertyNameException: Configuration property name '********' is not valid.


