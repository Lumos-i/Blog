# blog

#### 介绍
基于spingboot,MP, ES开发的个人博客项目

#### 软件架构
软件架构说明


#### 安装教程

1.  xxxx
2.  xxxx
3.  xxxx

#### 使用说明

1.  xxxx
2.  xxxx
3.  xxxx

```java 
# 配置端口
server:
  port: 8073
  servlet:
    session:
      timeout: 21600

# 配置mysql数据库
spring:
  datasource:
    type: com.zaxxer.hikari.HikariDataSource
    driver-class-name: com.mysql.cj.jdbc.Driver
    url: jdbc:mysql://*******:3306/blog?userUnicode=true&characterEncoding=utf-8&serverTimezone=UTC
    username: 
    password: 
    hikari:
      minimum-idle: 5
      # 空闲连接存活最大时间，默认600000（10分钟）
      idle-timeout: 180000
      # 连接池最大连接数，默认是10
      maximum-pool-size: 10
      # 此属性控制从池返回的连接的默认自动提交行为,默认值：true
      auto-commit: true
      # 连接池名称
      pool-name: MyHikariCP
      # 此属性控制池中连接的最长生命周期，值0表示无限生命周期，默认1800000即30分钟
      max-lifetime: 1800000
      # 数据库连接超时时间,默认30秒，即30000
      connection-timeout: 30000
      connection-test-query: SELECT 1
  # redis配置
  redis:
    host: 
    port: 6379
    password: 
  # mq配置
  rabbitmq:
    host: 
    port: 5672
    username: guest
    password: guest
    listener:
      simple:
        retry:
          enabled: true
          max-attempts: 3 #最大重试次数
          initial-interval: 3000 #重试间隔时间（单位毫秒）
  # es配置 若搜索模式为mysql可删除
#  elasticsearch:
#    rest:
#      uris: 
  # 邮箱配置
  mail:
    host: smtp.qq.com
    username: 
    password: 
    default-encoding: UTF-8
    port: 587
    properties:
      mail:
      smtp:
      auth: true
      socketFactory:
      class: javax.net.ssl.SSLSocketFactory
  # 上传图片大小限制
  servlet:
    multipart:
      max-file-size: 100MB
      max-request-size:  100MB

# 配置MybatisPlus
mybatis-plus:
  mapper-locations: classpath:mapper/*.xml
  configuration:
    log-impl: org.apache.ibatis.logging.stdout.StdOutImpl
    map-underscore-to-camel-case: true

# 搜索模式 可选 elasticsearch或mysql
search:
  mode: mysql


# 上传模式 可选 oss或local  （http://和最后的/一定不能去！！！）
upload:
  mode: local
  local:
    # nginx映射本地文件路径，无域名则为 ip:83
#    url: http://127.0.0.1:83/
    # 本地文件存储路径
    path: /usr/local/upload/
  oss:
    url: 
    endpoint: 
    accessKeyId: 
    accessKeySecret: 
    bucketName: 

  cos:
    url: 
    secretId: 
    secretKey: 
    region: 
    bucketName: 

# 网站前台域名（邮件通知用）
website:
  url: 

#第三方配置信息
qq:
  app-id: qqAPPID
  check-token-url: qq回调地址
  user-info-url: https://graph.qq.com/user/get_user_info?openid={openid}&access_token={access_token}&oauth_consumer_key={oauth_consumer_key}

#weibo:
#  app-id: 微博APPID
#  app-secret: 微博APPSECRET
#  grant-type: authorization_code
#  redirect-url: 微博回调地址
#  access-token-url: https://api.weibo.com/oauth2/access_token
#  user-info-url: https://api.weibo.com/2/users/show.json?uid={uid}&access_token={access_token}
```

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
