# EasyTopRelease
EasyTop发布页

这是专门的EasyTop部署教程!

# 服务端部署

环境要求Java版本>17

推荐Java版本: 17
## Linux与Windows环境
Q:如果没有配置文件直接启动会怎么样?A:也可以启动,不过无法使用邮件报警功能,端口默认是54781


从`Release`界面下载后首先制作配置文件`application.properties`
```agsl
spring.application.name=EasyTop
server.port=54781
spring.mail.host=###.###.com
spring.mail.port=###
spring.mail.username=###@###.com
spring.mail.password=#############
spring.mail.default-encoding=UTF-8
spring.mail.properties.mail.smtp.socketFactory.class=javax.net.ssl.SSLSocketFactory
spring.mail.properties.mail.debug=false
alert.email.to=###@#.com
```
配置文件讲解:
* spring.application.name: 服务名称
* server.port: 服务端口
* spring.mail.host: 邮箱服务器地址
* spring.mail.port: 邮箱服务器端口
* spring.mail.username: 邮箱用户名
* spring.mail.password: 邮箱密码(不是正常登录的那个密码)
* spring.mail.default-encoding: 邮箱编码
* spring.mail.properties.mail.smtp.socketFactory.class: 邮箱协议
* spring.mail.properties.mail.debug: 是否开启调试
* alert.email.to: 监控报警邮箱接收地址

之后启动项目即可,注意需要自己指定配置文件路径(比如同目录下)

```shell
java -jar ./EasyTop-0.0.1-SNAPSHOT.jar --spring.config.location=./application.properties
```

# 客户端配置
直接安装apk包即可

# 服务端API
| 路径              | 方法  | 描述       | 请求参数 | 响应   |
|-----------------|-----|----------|------|------|
| /api/sys/v1/all | GET | 获取机器运行信息 | 无    | Json |
| /api/sys/v1/uptime    | GET | 获取在线时长   | 无    | 启动时间 |
