### 1. 说明
只适用于使用logback日志框架   

### 2. 引入依赖

在使用 com.tydic.dev1:spring-boot-starter和com.tydic.dev1:spring-boot-starter-web，1.3.2-HW-SNAPSHOT以上版本会默认引入，如未使用前面2个包请单独引入com.tydic.dev1:spring-boot-starter-logging
```xml
<dependency>
    <groupId>com.tydic.dev1</groupId>
    <artifactId>spring-boot-starter-logging</artifactId>
</dependency>
```

### 3. 应用配置
在工程配置文件或nacos中添加如下配置  
简单配置
```
logging:
  config: classpath:logging-pub.xml #使用的配置文件logging-pub.xml（发布环境）或logging-dev.xml（发开环境），该配置文件在spring-boot-starter-logging包中

```
