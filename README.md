# jplogiccloud微服务架构平台实例

**项目介绍**

**一、功能点：**

   >该项目主要完成了RAC权限管理系统实例，并提供相关springcloud微服务架构运维监控组件（zipkin\turbine\hystrix-dashboard\spring boot admin\分布式swagger在线api）。
	
**二、技术点：**

   >核心技术为springcloud + akka + bootstrap等多个技术栈实现，基本都是采取了开源技术实现以及自研组件，该项目的技术栈只有部分技术采用的第三方服务是收费的，如阿里云的服务，基本上都是基于目前互联网公司常用的框架技术，可以为互联网创业公司解决微服务架构相关问题，可以帮助公司快速构建项目。本项目由多个后端springcloud微服务项目和1个前端web项目共同组成。实现了基于RBAC的权限管理（内部采用jwt+oauth2技术实现token无状态权限认证）解决方案，还可以基于该平台构建各种互联网公司的app服务端微服务架构以及认证体系等。
   
   
* 核心框架：springcloud Finchley.SR2全家桶
* 安全框架：spring security + springcloud Oauth2
* 分布式任务调度：elastic Job Lite
* 持久层框架：myBatis（myBatis-generator）、sharding-jdbc、mongo
* 数据库连接池：alibaba Druid
* 日志管理：logback	
*  前端框架：bootstrap以及其他第三方开源前端插件
* 第三方组件服务： 邮件服务、百度地图API
*  消息队列：kafka

**三、项目源代码结构：**

├── docs
│   ├── databases
│   └── scripts
├── jplogiccloud-apps
│   ├── jplogiccloud-app-crawler
│   ├── jplogiccloud-app-dfs
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
│   ├── jplogiccloud-starter-im-tencent
│   ├── jplogiccloud-starter-logger
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
│   ├── jplogiccloud-gateway.iml
│   ├── pom.xml
│   ├── src
│   └── target
├── jplogiccloud-master.iml
├── pom.xml
└── README.md

**作者介绍**

开源技术爱好者，springboot\springcloud\dubbo\大数据相关技术（spark\hadoop\kafka\scala）\容器docker等主流开源框架实践者，现在供职于一家互联网金融公司，负责两次公司项目组技术架构重构，在企业很多产品项目中实践目前主流的、社区活跃度很高的优秀技术；

**项目在线体验**

- 体验链接：<https://www.jplogic.cn/login> 

**技术QQ群交流**

![jplogiccloud群二维码](https://github.com/romantichjw/jplogiccloud/blob/master/images/jplogiccloud%E7%BE%A4%E4%BA%8C%E7%BB%B4%E7%A0%81.png "jplogiccloud群二维码")

**微信交流群**

<img src="https://github.com/romantichjw/jplogiccloud/blob/master/images/jplogiccloud%E5%BE%AE%E4%BF%A1%E4%BA%A4%E6%B5%81%E7%BE%A4.jpg" width="199px" height="264px"></img>

**项目截图演示**

1、日志控制台
![日志控制台](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E6%97%A5%E5%BF%97%E6%8E%A7%E5%88%B6%E5%8F%B0.png "日志控制台")

2、角色管理-列表
![角色管理-列表](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E8%A7%92%E8%89%B2%E7%AE%A1%E7%90%86-%E5%88%97%E8%A1%A8.png "角色管理-列表")

3、角色管理-新增
![角色管理-新增](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E8%A7%92%E8%89%B2%E7%AE%A1%E7%90%86-%E6%96%B0%E5%A2%9E.png "角色管理-新增")

4、部门管理-主页
![部门管理-主页.](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E9%83%A8%E9%97%A8%E7%AE%A1%E7%90%86-%E4%B8%BB%E9%A1%B5.png "部门管理-主页.")

5、菜单管理-主页
![菜单管理-主页](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E8%8F%9C%E5%8D%95%E7%AE%A1%E7%90%86-%E4%B8%BB%E9%A1%B5.png "菜单管理-主页")

6、菜单管理-新增资源权限
![菜单管理-新增资源权限](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E8%8F%9C%E5%8D%95%E7%AE%A1%E7%90%86-%E6%96%B0%E5%A2%9E%E8%B5%84%E6%BA%90%E6%9D%83%E9%99%90.png "菜单管理-新增资源权限")

7、菜单管理-权限资源设置
![菜单管理-权限资源设置](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E8%8F%9C%E5%8D%95%E7%AE%A1%E7%90%86-%E6%9D%83%E9%99%90%E8%B5%84%E6%BA%90%E8%AE%BE%E7%BD%AE.png "菜单管理-权限资源设置")

8、菜单管理-菜单设置
![菜单管理-菜单设置](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E8%8F%9C%E5%8D%95%E7%AE%A1%E7%90%86-%E8%8F%9C%E5%8D%95%E8%AE%BE%E7%BD%AE.png "菜单管理-菜单设置")

9、用户管理-列表
![用户管理-列表](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E7%94%A8%E6%88%B7%E7%AE%A1%E7%90%86-%E5%88%97%E8%A1%A8.png "用户管理-列表")

10、用户管理-登录ip
![用户管理-登录ip](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E7%94%A8%E6%88%B7%E7%AE%A1%E7%90%86-%E7%99%BB%E5%BD%95ip.png "用户管理-登录ip")

11、用户管理-编辑
![用户管理-编辑](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E7%94%A8%E6%88%B7%E7%AE%A1%E7%90%86-%E7%BC%96%E8%BE%91.png "用户管理-编辑")

12、权限管理-主页
![权限管理-主页](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E6%9D%83%E9%99%90%E7%AE%A1%E7%90%86-%E4%B8%BB%E9%A1%B5.png "权限管理-主页")

13、日志管理-主页
![日志管理-主页](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E6%97%A5%E5%BF%97%E7%AE%A1%E7%90%86-%E4%B8%BB%E9%A1%B5.png "日志管理-主页")

14、布局设置
![布局设置](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E5%B8%83%E5%B1%80%E8%AE%BE%E7%BD%AE.png "布局设置")

15、布局设置-上下结构
![布局设置-上下结构](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E5%B8%83%E5%B1%80%E8%AE%BE%E7%BD%AE-%E4%B8%8A%E4%B8%8B%E7%BB%93%E6%9E%84.png "布局设置-上下结构")

16、springbootadmin管理
![springbootadmin管理](https://github.com/romantichjw/jplogiccloud/blob/master/images/springbootadmin%E7%AE%A1%E7%90%86.png "springbootadmin管理")

18、分布式api文档管理
![分布式api文档管理](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E5%88%86%E5%B8%83%E5%BC%8Fapi%E6%96%87%E6%A1%A3%E7%AE%A1%E7%90%86.png "分布式api文档管理")

19、分布式任务调度管理
![分布式任务调度管理](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E5%88%86%E5%B8%83%E5%BC%8F%E4%BB%BB%E5%8A%A1%E8%B0%83%E5%BA%A6%E7%AE%A1%E7%90%86.png "分布式任务调度管理")

20、分布式调用轨迹跟踪管理
![分布式调用轨迹跟踪管理](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E5%88%86%E5%B8%83%E5%BC%8F%E8%B0%83%E7%94%A8%E8%BD%A8%E8%BF%B9%E8%B7%9F%E8%B8%AA%E7%AE%A1%E7%90%86.png "分布式调用轨迹跟踪管理")

21、服务注册发现管理
![服务注册发现管理](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E6%9C%8D%E5%8A%A1%E6%B3%A8%E5%86%8C%E5%8F%91%E7%8E%B0%E7%AE%A1%E7%90%86.png "服务注册发现管理")

22、服务熔断监控管理
![服务熔断监控管理](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E6%9C%8D%E5%8A%A1%E7%86%94%E6%96%AD%E7%9B%91%E6%8E%A7%E7%AE%A1%E7%90%86.png "服务熔断监控管理")
