# longdemo
long写的demo都搁这了

# 本项目将实现“企业级微服务框架项目”所需的众多技术的demo，包括但不限于：
* 统一认证功能
  * 网关统一认证
  * url级权限控制
  * 支持oauth2的四种模式登录
  * 支持用户名、密码加图形验证码登录
  * 支持手机号加密码登录
  * 支持openId登录
  * 支持第三方系统单点登录
* 分布式系统基础支撑
  * 服务注册发现、路由与负载均衡
  * 服务降级与熔断
  * 服务限流(url/方法级别)
  * 统一配置中心
  * 统一日志中心
  * 统一搜索中心
  * 统一分布式缓存操作类、cacheManager配置扩展
  * 分布式锁
  * 分布式任务调度器
  * 支持CI/CD持续集成(包括前端和后端)
  * 分布式Id生成器
  * 分布式事务(强一致性/最终一致性)
  * 日志链路追踪
* 系统监控功能
  * 服务调用链监控
  * 应用拓扑图
  * 应用统一日志查询
  * 慢查询SQL监控
  * 应用吞吐量监控(qps、rt)
  * 服务降级、熔断监控
  * 服务限流监控
  * 微服务服务监控
  * 服务器监控
  * redis监控
  * mysql监控
  * elasticSearch监控
  * nacos监控
  * prometheus监控
* 业务基础功能支撑
  * 多租户(应用隔离)
  * 高性能方法级幂等性支持
  * RBAC权限管理，实现细粒度控制(方法、url级别)
  * 快速实现导入、导出功能
  * 数据库访问层自动实现crud操作
  * 代码生成器
  * 基于Hutool的各种便利开发工具
  * 网关聚合所有Swagger接口文档
  * 统一跨域处理
  * 统一异常处理
# 组件选择
* 分布式系统套件版本：Spring Boot 2.x + Spring Cloud + Spring Cloud Alibaba
* 服务治理注册与发现：Spring Cloud Alibaba Nacos
* 统一配置中心：Spring Cloud Alibaba Nacos
* 服务降级、熔断和限流：alibaba/Sentinel
* 网关路由代理调用：Spring Cloud Gateway / Netflix Zuul
* 声明式服务调用：Spring Cloud OpenFeign
* 服务负载均衡：Spring Cloud Netflix Ribbon
* 服务安全认证：Spring Security
* 数据访问层：Mybatis-plus
* 分布式事务：alibaba/Seata / RocketMQ
* 统一日志收集存储：ELK + Filebeat
* 服务应用监控：Spring Cloud Admin / Prometheus
* 服务调用链监控：Skywalking
* 分布式任务调度：XXL-JOB
* 全文搜索引擎：Elasticsearch
* 分库分表：Sharding-JDBC
* 容器管理平台：Rancher
# 组件对比
## 服务注册发现
  * Nacos 对比 Eureka
    * eureka闭源了，所以不作考虑
    * nacos是目前比较看好的后起之秀，并且是ap模型非常适合注册中心支持多机房部署；同时无缝对接与支持dubbo、spring cloud和kubernates云原生体系


## 配置中心
  * Nacos 对比 Apollo
    * Nacos缺点：目前的版本在功能上还是比apollo要少点，主要体现在发布审计、灰度发布等功能。
    * Nacos优点：支持yml格式，并且和注册中心是同一套中间件，方便管理运维


## 服务降级、熔断和限流
* Sentinel 对比 Hystrix
  * hystrix停止更新了
  * sentinel 的功能比hystrix要多，主要为以下几点
    * 支持动态配置规则(业务无入侵)
    * 支持系统负载保护(根据自定义规则总体保护，不限于某个接口)
    * 完善的控制台(开箱即用、可配置规则、秒级监控、机器发现等)

# 备注
  * APM应用性能管理（SkyWalking）
  * ELK日志系统（ElasticSearch、Logstash、Kibana）
    * ElasticSearch是一个基于Lucene的搜索服务器
    * Logstash，数据分析工具
    * Kibana，分析与可视化平台，用来搜索、查看存储在Elasticsearch索引中的数据
  * GPE监控预警系统（Grafana+Prometheus+Exporter）
    * Grafana度量分析和可视化工具
    * Prometheus服务监控系统,
    * Exporter,向Prometheus提供监控样本数据的程序、Exporter的一个实例称为target，Prometheus通过轮询的方式定期从这些target中获取样本数据。
  * [TX-LCN分布式事务管理](https://github.com/codingapi/tx-lcn) 
  * Nginx
  * Nacos
  * Zuul
  * Ribbon
  * feign
  * Sentinel
  * OSS
  * canal，mysql的实时数据订阅组件，canal-adapter、canal-server 
  * RocketMQ
  * Redis

![image](https://user-images.githubusercontent.com/44282487/140855734-886292ae-1f1b-4c4b-a3ba-c6631fa16109.png)

