# jplogiccloud微服务架构平台-微服务快速开发脚手架

**项目介绍**

**一、功能点：**

   >该项目主要是RBAC权限管理系统实例（系统管理、用户管理、角色管理等），基于Springcloud企业级微服务架构的快速开发脚手架，除了能够快速的构建权限管理系统之外同时也能够快速基于该脚手架快速构建企业级产品（互联网APP、Saas系统等），并提供相关springcloud微服务架构运维监控组件（zipkin\turbine\hystrix-dashboard\spring boot admin\分布式swagger在线文档）以及集成了主流的APM监控运维体系Skywalking(对标springcloud的zipkinServer)、集成了GPE（Grafana +Prometheus+Exporters）系统监控系统，同时也集成了ELK日志收集平台，能够把一整套目前互联网公司主流技术栈全套迁移到各个企业中去，并根据需要灵活定制，同时提供一整套企业级CI/CD解决方案，支持Docker/K8s服务容器化自动化。
	
**二、技术点：**

   >该脚手架集成了丰富的spring-boot-starter，可根据企业的产品功能的需要灵活装配需要的组件，这让开发人员花更多的时间在使用这些集成好的组件完成具体的业务逻辑，并能够通过平台提供的各种监控体系构件很清楚的了解系统服务生命周期过程中的各种指标状态，基本上采用了开源技术实现以及自研组件，因此基于微服务架构开源标准，目前的开发人员很容易上手使用，可以为互联网创业公司解决微服务架构相关问题，可以帮助公司快速构建项目。本项目由多个后端springcloud微服务项目和1个前端web项目共同组成。实现了基于RBAC的权限管理解决方案，还可以基于该平台构建各种互联网公司的app服务端微服务架构以及认证体系等。
   
   
* 核心框架：Greenwich.SR5全家桶
* 安全框架：spring security + springcloud Oauth2
* 事件驱动EDA框架：akka-standalone模式、akka-cluster模式
* 分布式搜素引擎框架：ElasteSearch 
* 腾讯IM SDK：IM starter
* 分布式任务调度：Elastic Job Lite + XXL-JOB
* 持久层框架：myBatis（myBatis-generator）、sharding-jdbc、mongo
* 数据库连接池：alibaba Druid
* 日志管理：ELK(Log-pilot)
* OSS文件存储：oss-aliyun、oss-fastdfs、oss-minio、oss-qiniucloud (按照公司技术选型要求灵活集成)
* 监控体系：GPE(Grafana + Prometheus + Exporters(Sofa-lookout监控[基于eureka服务发现]等各种Exporter))
* 分布式服务调用链跟踪服务以及APM：ZinkinServer + Skywalking(以及微服务docker镜像集成skywaling_agent) 
* 前端框架：bootstrap以及其他第三方开源前端插件
* 第三方组件服务： 邮件服务、百度地图API
* 消息队列：kafka + rabbitmq + rocketmq 
* 大数据存储：hbase
* 反爬虫检查：api资源反爬虫检查
* Ocr实名认证：阿里云ocr服务（ocr-starter）
* 消息推送服务：极光推送
* 短信服务：阿里云短信服务 +　第三方短信服务　短信服务路由
* 服务降级：alibaba-sentinel＋springcloud-Hystrix
* 分布式事务：alibaba-seata ＋ txlcn + mq消息最终一致性事务控制
* CI/CD：GIT + Gitlab + Nexus + Maven + Jenkins Pipline + Sonar + Harbor + Docker + K8s 
* 分布式配置：Apollo + Nacos
* 分库分表：Sharding-jdbc- + Mycat

**三、功能简述：**

* 集成了oauth2多种认证方式
（手机号、openId、图形验证码、第三方系统授权登陆，如微信开发平台、支付宝等）以及认证模式；
* 服务注册发现、
* 路由与负载均衡
* 服务降级与熔断
* 服务资源反爬虫验证
* 支持多种分布式配置中心
* 支持多种日志平台
* 缓存+lua并发支持 
* 支持多种分布式锁
* 应用命令行
* 分布式任务调度
* 分布式事务管理
* 支持CI/CD持续集成
* 分布式高性能Id生成器（大厂使用的方案）
* 系统监控基础设施
* 服务调用链监控
* 微服务应用监控
* 慢查询SQL监控
* 服务限流监控
* RBAC权限管理
* 数据库分库分表
* 聚合的Swagger接口文档
* IM聊天模块
* 搜索引擎
* 经纬坐标翻译
* 支持多种分布式文件存储
* 事件驱动
* 容器化部署

**四、架构图：**

![架构图](http://image.jplogic.cn/img/Jplogiccloud-archecture.jpg "架构图")

**五、项目源代码结构：**


├── docs  
│   ├── databases    
│   └── scripts   
├── jplogiccloud-apps  
│   ├── jplogiccloud-app-crawler   
│   ├── jplogiccloud-app-dfs   
│   ├── jplogiccloud-app-keygen   
│   ├── jplogiccloud-app-platmgr   
│   └── pom.xml     
├── jplogiccloud-bootstarter     
│   ├── jplogiccloud-bootstarter.iml   
│   ├── jplogiccloud-starter-akka-cluster    
│   ├── jplogiccloud-starter-akka-standalone   
│   ├── jplogiccloud-starter-email   
│   ├── jplogiccloud-starter-es     
│   ├── jplogiccloud-starter-fraudcheck    
│   ├── jplogiccloud-starter-geo    
│   ├── jplogiccloud-starter-hbase    
│   ├── jplogiccloud-starter-im-tencent   
│   ├── jplogiccloud-starter-logger   
│   ├── jplogiccloud-starter-mq-kafka    
│   ├── jplogiccloud-starter-mq-rabbit    
│   ├── jplogiccloud-starter-oauth2-feign    
│   ├── jplogiccloud-starter-ocr-alicloud    
│   ├── jplogiccloud-starter-oss-alicloud    
│   ├── jplogiccloud-starter-oss-base   
│   ├── jplogiccloud-starter-oss-fastdfs   
│   ├── jplogiccloud-starter-oss-minio   
│   ├── jplogiccloud-starter-oss-qiniucloud   
│   ├── jplogiccloud-starter-prometheus   
│   ├── jplogiccloud-starter-redis   
│   ├── jplogiccloud-starter-sentinel   
│   ├── jplogiccloud-starter-sms-alicloud    
│   ├── jplogiccloud-starter-sqllog   
│   ├── jplogiccloud-starter-zookeeper   
│   └── pom.xml   
├── jplogiccloud-common   
│   ├── jplogiccloud-common-core   
│   ├── jplogiccloud-common.iml   
│   ├── jplogiccloud-common-security   
│   └── pom.xml    
├── jplogiccloud-component   
│   ├── jplogiccloud-component.iml   
│   ├── jplogiccloud-component-tracer   
│   ├── jplogiccloud-component-ws   
│   └── pom.xml   
├── jplogiccloud-dao    
│   ├── jplogiccloud-dao-base    
│   ├── jplogiccloud-dao-file   
│   ├── jplogiccloud-dao.iml    
│   ├── jplogiccloud-dao-lgc   
│   ├── jplogiccloud-dao-sys   
│   └── pom.xml   
├── jplogiccloud-environment   
│   ├── jplogiccloud-admin-server    
│   ├── jplogiccloud-config-server    
│   ├── jplogiccloud-environment.iml    
│   ├── jplogiccloud-monitor-dashboard    
│   ├── jplogiccloud-monitor-prometheus-grafana    
│   ├── jplogiccloud-monitor-skywalking    
│   ├── jplogiccloud-monitor-zipkin    
│   ├── jplogiccloud-registrycenter-eureka    
│   ├── jplogiccloud-registrycenter-nacos    
│   ├── jplogiccloud-sentinel-dashboard   
│   └── pom.xml    
├── jplogiccloud-gateway    
│   ├── build-image.sh      
│   ├── Dockerfile   
│   ├── IMAGE_NAME   
│   ├── jplogiccloud-gateway.iml    
│   ├── pom.xml   
│   ├── src    
│   ├── TAG_NAME    
│   └── target    
├── jplogiccloud-master.iml    
├── package-dev.bat    
├── package-dev.sh    
├── package-pro.bat    
├── package-pro.sh    
├── package-test.bat    
├── package-test.sh    
├── pom.xml    
└── README.md   



**作者介绍**

开源技术爱好者，springboot\springcloud\dubbo\大数据相关技术（spark\hadoop\kafka\scala）\容器docker等主流开源框架实践者，曾在多家互联网公司担任技术负责人兼高级架构师，负责过多个从零1互联网项目，从事医疗、金融、区块链等行业，有丰富的互联网经验，非常欢迎与大家进行相关交流；

**项目在线体验**

- 体验链接：<https://www.jplogic.cn/login>   登陆账号admin/huangjianwen

**技术QQ群交流**

![jplogiccloud群二维码](http://image.jplogic.cn/img/Jplogiccloud-qcode2.png "jplogiccloud群二维码")

**微信交流群**

<img src="http://image.jplogic.cn/img/jplogiccloud-wechat-qun.jpg" width="199px" height="264px"></img>

**项目CI/CD可持续集成演示**

![cicd](http://image.jplogic.cn/img/show-gitlab.png "cicd")
![cicd](http://image.jplogic.cn/img/show-sonar.png "cicd")
![cicd](http://image.jplogic.cn/img/show-jenkins.png "cicd")
![cicd](http://image.jplogic.cn/img/show-harbor.png "cicd")

**项目GPE监控预警演示**

![monitor](http://image.jplogic.cn/img/show-grafana1.png "monitor")
![monitor](http://image.jplogic.cn/img/show-grafana2.png "monitor")
![monitor](http://image.jplogic.cn/img/show-grafana3.png "monitor")
![monitor](http://image.jplogic.cn/img/show-grafana4.png "monitor")

**项目APM调用轨迹跟踪以及性能演示**

![monitor](http://image.jplogic.cn/img/show-skywalking1.png "monitor")
![monitor](http://image.jplogic.cn/img/show-skywalking2.png "monitor")
![monitor](http://image.jplogic.cn/img/show-skywalking3.png "monitor")

**项目截图演示**

1、日志控制台
![日志控制台](http://image.jplogic.cn/img/log-console.png "日志控制台")

2、角色管理-列表
![角色管理-列表](http://image.jplogic.cn/img/role-list.png "角色管理-列表")

3、角色管理-新增
![角色管理-新增](http://image.jplogic.cn/img/role-add.png "角色管理-新增")

4、部门管理-主页
![部门管理-主页.](http://image.jplogic.cn/img/dept1.png "部门管理-主页.")

5、菜单管理-主页
![菜单管理-主页](http://image.jplogic.cn/img/tree-mgr1.png "菜单管理-主页")

6、菜单管理-新增资源权限
![菜单管理-新增资源权限](http://image.jplogic.cn/img/tree-mgr1.png "菜单管理-新增资源权限")

7、菜单管理-权限资源设置
![菜单管理-权限资源设置](http://image.jplogic.cn/img/tree-mgr2.png "菜单管理-权限资源设置")

8、菜单管理-菜单设置
![菜单管理-菜单设置](http://image.jplogic.cn/img/tree-mgr3.png "菜单管理-菜单设置")

9、用户管理-列表
![用户管理-列表](http://image.jplogic.cn/img/user-list.png "用户管理-列表")

10、用户管理-登录ip
![用户管理-登录ip](http://image.jplogic.cn/img/user-login.png "用户管理-登录ip")

11、用户管理-编辑
![用户管理-编辑](http://image.jplogic.cn/img/user-edit.png "用户管理-编辑")

12、权限管理-主页
![权限管理-主页](http://image.jplogic.cn/img/pers.png "权限管理-主页")

13、日志管理-主页
![日志管理-主页](http://image.jplogic.cn/img/log-list.png "日志管理-主页")

14、布局设置
![布局设置](http://image.jplogic.cn/img/layout-setting.png "布局设置")

15、布局设置-上下结构
![布局设置-上下结构](http://image.jplogic.cn/img/layout-setting-up-down.png "布局设置-上下结构")

16、springbootadmin管理
![springbootadmin管理](http://image.jplogic.cn/img/springbootadmin.png "springbootadmin管理")

18、分布式api文档管理
![分布式api文档管理](http://image.jplogic.cn/img/swagger-api.png "分布式api文档管理")

19、分布式任务调度管理
![分布式任务调度管理](http://image.jplogic.cn/img/elastic-job.png "分布式任务调度管理")

20、分布式调用轨迹跟踪管理
![分布式调用轨迹跟踪管理](http://image.jplogic.cn/img/trace.png "分布式调用轨迹跟踪管理")

21、服务注册发现管理
![服务注册发现管理](http://image.jplogic.cn/img/register.png "服务注册发现管理")

22、服务熔断监控管理
![服务熔断监控管理](http://image.jplogic.cn/img/hystrix.png "服务熔断监控管理")
