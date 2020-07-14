### 验证

在 FUN-BOOT 中是从二点去验证的：

- 是否过期以及是否和缓存中的JWT一致。

- 要知道，如果JWT的 payload 被修改后，是不能被正常解开的，所以验证能否正常解开当前JWT并读取其中属性即可。

### 免检

不需要登录就能够访问某些接口，可以通过 `@PassToken`来实现。使用示例如下：

```java
    @PassToken
    @PostMapping("/rsa/keys")
    public CommonResult getRsaKeys(String loginName) {
        encryptService.initRsa(loginName);
        return success(encryptService.genRsaKeys());
    }
```


