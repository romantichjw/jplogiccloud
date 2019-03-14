# jplogiccloud个人微服务架构平台实例

**项目介绍**

**功能点：**

   >该项目主要完成了RAC权限管理系统实例，并提供相关springcloud微服务架构运维监控组件（zipkin\turbine\hystrix-dashboard\spring boot admin\分布式swagger在线api）。
	
**技术点：**

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
