## JDK

因为项目用到了JDK 8的一些特性，所以JDK最低版本不能低于8。

JDK 8官方下载地址：[https://www.oracle.com/technetwork/java/javase/downloads](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)。

（附：如果JDK和项目的下载速度慢，可在Q群获取）

## Redis

脚手架使用的缓存是Redis，所以在导入项目之前需要先安装Redis。

Windows系统：

- [下载直通车](https://github.com/MicrosoftArchive/redis/releases)
  
  下载完成后，解压出来之后，使用cmd命令切换到Redis根目录，然后运行
  
  `redis-server.exe redis.windows.conf`启动即可。项目中与Redis相关的配置可在application-dev.yml 中修改：
  
  ```yaml
  spring:
    redis:
      # Redis数据库索引（默认为 0）
      database: 0
      # Redis服务器地址
      host: 127.0.0.1
      # Redis服务器连接端口
      port: 6379
      # Redis 密码
      password:
      jedis:
        pool:
          # 连接池中的最小空闲连接
          min-idle: 8
          # 连接池中的最大空闲连接
          max-idle: 500
          # 连接池最大连接数（使用负值表示没有限制）
          max-active: 2000
          # 连接池最大阻塞等待时间（使用负值表示没有限制）
          max-wait: 10000
      # 连接超时时间（毫秒）
      timeout: 300
  ```

Linux系统：

- 方法一，使用docker快速部署。
  
  教程：https://www.runoob.com/docker/docker-install-redis.html

- 方法二，源码安装。
  
  **获取源码**
  
  ```bash
  wget http://download.redis.io/releases/redis-5.0.3.tar.gz
  ```
  
  **解压**
  
  ```bash
  tar xzf redis-5.0.3.tar.gz
  ```
  
  **编译**
  
  ```bash
  make
  ```
  
  **安装**
  
  当前选择的是安装在 /usr/local/ 目录，安装位置根据个人而定。
  
  ```bash
  make PREFIX=/usr/local/redis install
  ```
  
  安装完后，在/usr/local/redis/bin下有以下几个可执行文件：

| 文件名             | 作用                 |
|:---------------:|:------------------:|
| redis-benchmark | 性能测试工具             |
| redis-check-aof | AOF文件修复工具          |
| redis-check-rdb | RDB文件检查工具（快照持久化文件） |
| redis-cli       | 命令行客户端             |
| redis-server    | redis服务器启动命令       |

  检查当前目录下是否存在redis.conf 这个文件，若不存在，将配置文件移动 /usr/local/redis

```bash
  cp redis.conf /usr/local/redis
```

  **启动Redis**

```bash
  ./redis-sever
```

## MySQL

脚手架的数据库采用的是MySQL版本为5.7的社区版。

下载地址：[https://dev.mysql.com/downloads/windows/installer/5.7.html](https://dev.mysql.com/downloads/windows/installer/5.7.html)

别的版本的MySQL也可以，但需要根据实际情况修改对应的SQL语句。
