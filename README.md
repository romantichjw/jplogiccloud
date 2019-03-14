# jplogiccloud个人微服务架构平台实例

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

>jplogiccloud-master
>>jplogiccloud-environment ===> springcloud运行环境，包含注册中心、SBA(spring boot admin)、配置中心、hystrix监控白板、zipkin分布式轨迹跟踪监控管理工具、注册中心（eureka\consul）
>>>
    jplogiccloud-admin-server（spring boot admin）
    jplogiccloud-config-server（配置中心）
    jplogiccloud-monitor-dashboard（hystrix监控白板）
    jplogiccloud-monitor-zipkin（zipkin分布式轨迹跟踪监控管理工具）
    jplogiccloud-registrycenter-eureka（注册中心-eureka）
>>jplogiccloud-common ===> 公共工具模块，主要负责定义公共工具或者核心工具类模块
>>>
    jplogiccloud-common-core（定义项目所有模块都有可能公用的工具，注意：不允许在该模块定义springboot自动启动配置类）
    jplogiccloud-common-security（定义oauth2安全认证相关的基础工具封装）
>>jplogiccloud-component ===> 公共组件模块，主要负责定义第三方组件模块
>>>
    jplogiccloud-component-akka（定义akka组件，基于事件驱动的轻量级组件）
    jplogiccloud-component-tracer（定义zipkin分布式轨迹跟踪信息上报组件）
    jplogiccloud-component-wf（定义工作流组件）
    jplogiccloud-component-ws（定义websocket相关自动配置组件）
>>jplogiccloud-dao ===> 数据访问层dao（mongo\mysql）模块,提供分库分表操作相关配置
>>>
    jplogiccloud-dao-base（定义数据访问层（mongo\mysql）基础类）
    jplogiccloud-dao-sys（定义系统中心库entity、mapper映射以及分库分表定义配置）
    jplogiccloud-dao-lgc（定义日志中心库entity、mapper映射以及分库分表定义配置）
>>jplogiccloud-gateway ===> zuul网关模块,主要负责请求路由、限流、权限等功能
>>jplogiccloud-apps ===> 平台扩展应用模块
>>>
    jplogiccloud-app-crawler（定义爬虫应用模块）
    jplogiccloud-app-platmgr（定义RAC权限框里后台以及其他应用后台模块）
>>>>
    jplogiccloud-app-platmgr-console-web（定义平台管理控制台前端web应用）
    jplogiccloud-app-platmgr-provider-api（定义平台管理后台feign Client以及各个微服务model【vo、dto、vo、enums、constants】）
    jplogiccloud-app-platmgr-provider-lgc（定义平台日志中心微服务api提供者，包含oauth2资源服务中心）
    jplogiccloud-app-platmgr-provider-sys（定义平台系统中心微服务api提供者，包含oauth2认证服务中心以及自身资源服务中心）
>>>
>>>
>>docs ===> 项目必要文档，主要是项目数据库脚本等；

**项目截图演示**
1、日志控制台
![日志控制台](https://github.com/romantichjw/jplogiccloud/blob/master/images/%E6%97%A5%E5%BF%97%E6%8E%A7%E5%88%B6%E5%8F%B0.png "日志控制台")
