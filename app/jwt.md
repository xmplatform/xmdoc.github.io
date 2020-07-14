`JJWT`是基于`JWT`的一个开源框架。项目地址及文档：https://github.com/jwtk/jjwt

在项目中使用 JWT 的场景是鉴权，那么不得不考虑安全问题，为了防止重放攻击，有四个策略：加密、时间戳、nonce、时间戳 + nonce。

**①加密**

可以使用RSA算法，但是略为复杂，若是非常重要的数据，那么建议使用，在项目中也提供了一个RSA的工具类。

**②时间戳**

在请求中夹带一个时间戳，设置较短的有效期。如果一个新来的请求的请求时间超过了请求中的有效期，则认为无效。此策略也有问题，若是真有人在这个有效期内，仍然能完成重放。在项目中可以在`fun-boot.properties`中修改JWT的过期时间，也可通过App来主动刷新JWT使得旧的JWT过期。

**③nonce**

在请求中夹带一个随机字符串，这个字符串传送到客户端后即存入客户端的黑名单中，如果一个新来的请求其中存在的随机字符串已经在黑名单中则认为无效。但是显然，这个策略存在巨大的问题：服务端需要维护一个黑名单库，可以把这个库放到 redis 缓存中，但是这个库的大小会随着业务运行的时间而变得越来越大，从而影响性能（大项目除外）。

**④时间戳 + nonce**

在请求中夹带一个随机字符串和一个时间戳，如果一个新来的请求，其随机字符串已经在黑名单中则认为无效，或者一个请求的的请求时间超过了其有效期，则也认为其无效。这样黑名单的范围只需设置为时间戳策略的有效期范围即可。这种策略对应到 JWT 中就是给 token 既设置一个黑名单，又设置一个有效期。

### FUN-BOOT是如何使用JWT的？

在用户登录成功后，生成一个 JWT，并将当前用户信息和 JWT 存入 redis ，若登录时存在参数 rememberMe的值为 true 则默认登录状态保留七天，反之为三天。在项目中，默认拦截`/app/**`下所有的接口都需要登录后访问。拦截请求时，会从请求体中去获取Authorization 这个属性的 JWT ，并对当前 JWT 进行验证，验证失败返回`{"code": 401,"data": false,"message": "未登录或token已经过期"}`。登录成功后返回如下JSON数据：

```json
{
    "code": 200,
    "message": "登录成功",
    "data": {
        "perms": [
            "user:view",
            "user:edit",
            "user:delete"
        ],
        "user": {
            "createTime": 1574840737034,
            "updateTime": 1574998261698,
            "status": "1",
            "createBy": null,
            "updateBy": null,
            "searchValue": null,
            "remark": "",
            "params": {},
            "userId": 4,
            "loginName": "test02",
            "username": "竹影清风",
            "userLevel": 1,
            "email": "903131009@qq.com",
            "sex": "2",
            "password": "it's a secret",
            "salt": "it's a secret",
            "avatar": "/fun/img/avatar/default.png",
            "telephone": "13212101110",
            "delFlag": "1",
            "loginIp": "127.0.0.1",
            "loginDate": 1575462006501,
            "openId": "191127118986171744253",
            "isLock": "0",
            "honor": 400,
            "exp": 0,
            "fansNum": 0,
            "followNum": 0,
            "oid": "4",
            "health": 100,
            "banTime": null,
            "isVerify": "0",
            "roleId": null,
            "roleKey": "regist",
            "roleName": "注册用户",
            "uaccount": "191127B6YBCDAMRP"
        },
        "token": "eyJhbGciOiJIUzI1NiJ9.eyJyb2xlX2tleSI6InJlZ2lzdCIsImlzcyI6Ik1yREp1biIsInN1YiI6InRlc3QwMiIsImF1ZCI6IjQiLCJpYXQiOjE1NzU1NTI0NjZ9.odvBtDbePqCqmXJ_PO57nV9igByB_EtdgLWRBQKpqRQ"
    }
}
```

当App端在访问`/app/refreshToken`刷新 JWT 后，直接替换缓存中的 JWT ，这样就可以保证让之前的JWT失效，同时也会刷新缓存中用户的个人信息。

当然，当用户在退出登录的时候，也需要从缓存中将当前用户的个人信息和 JWT 一同清除，所以在退出时需要访问`/app/logout`接口。
