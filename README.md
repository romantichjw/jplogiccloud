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

**作者介绍**

开源技术爱好者，springboot\springcloud\dubbo\大数据相关技术（spark\hadoop\kafka\scala）\容器docker等主流开源框架实践者，现在供职于一家互联网金融公司，负责两次公司项目组技术架构重构，在企业很多产品项目中实践目前主流的、社区活跃度很高的优秀技术；

**项目在线体验**

- 体验链接：<http://47.94.216.49:7477/login> 

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
