## 1. maven配置
```xml
        <dependency>
            <groupId>com.alibaba.cloud</groupId>
            <artifactId>spring-cloud-starter-alibaba-sentinel</artifactId>
        </dependency>
        <dependency>
            <groupId>com.alibaba.csp</groupId>
            <artifactId>sentinel-datasource-nacos</artifactId>
        </dependency>
```

## 2. 程序配置

```yaml
spring:
  cloud:
    sentinel:
      datasource:
        degrade:
          nacos:
            namespace: ${nacos-namespace}
            server-addr: ${nacos-addr}
            data-id: sentinel.json
            rule-type: degrade
            group-id: example
            flow:
              nacos:
                namespace: ${nacos-namespace}
                server-addr: ${nacos-addr}
                data-id: flow.json
                rule-type: flow
                group-id: example
            system:
              nacos:
                namespace: ${nacos-namespace}
                server-addr: ${nacos-addr}
                data-id: system.json
                rule-type: system
      transport:
        dashboard: localhost:7021
      enabled: true
```
## 3. 控制台启动
```shell
java -Dserver.port=7021 -Dproject.name=sentinel-dashboard -jar sentinel-dashboard.jar
```
## 4. feign配置
```yml
feign:
  sentinel:
    enabled: true
```

## 4. feign熔断配置
```yml
feign:
  sentinel:
    enabled: true
  client:
    config:
      default:
        connectTimeout: 1000 #连接超时
        readTimeout: 60000 #读取数据超时
```
控制台配置

![image.png](0)
![image.png](1)



