# Springboot的重要性

简化部署、简化配置、简化编码、快速创建

## SpringBoot启动流程解析

章节目录

### ·一：环境准备

·Java8、·Maven3.3、·IntelliJIDEA、·Mysql5.7+

#### Java8新特性

`·Lambda表达式、·Stream操作、·接口默认&静态方法、·方法引用、·重复注解、·类型注解、·日期&时间API、·base64加解密API、·数组并行操作、·JVM新增元空间`

#### Maven优点

`·依赖管理，项目构建·生命周期·插件机制`

#### IntelliJIDEA

`·强大的整合能力、·提示功能快速、便捷、·快捷键方便、·简洁易用的GUI界面`

#### Mysql

`·性能卓越、·服务稳定、·开放源代码、·社区活跃`

### ·二：动手搭建SSM与SpringBoot框架对比

SSM框架介绍 spring(现代Java源泉)+spring mvc(基于MVC的web框架)+MyBatis(基于ORM的数据框架)

### ·三：启动流程介绍

`SSM搭建流程：start->引入jar包->web.xml->applicationContext.xml->dispatcherServlet.xml->mybatis-config.xml->配置容器->编写服务类->编写控制类->end`
SSM搭建总结:·耗时长、·配置文件繁琐、·jar包管理、·新手不友好
`SpringBoot搭建流程:start->引入starter->application.properties->编写服务类->编写控制类->end`
SpringBoot搭建总结：·耗时短、·配置文件简洁、·不关注版本管理、·易上手

### 启动流程介绍

#### ·框架初始化

框架初始化步骤
配置资源加载器
配置primarySources
应用环境检测
配置系统初始化器
配置应用监听器
配置main方法所在类

#### ·框架启动

启动框架:计时器开始计时->Headless模式赋值->发送ApplicationStartingEvent->配置环境模块->发送ApplicationEnvironmentPreparedEvent->打印banner->创建应用上下文对象->初始化失败分析器->关联springboot组件与应用上下文对象->发送ApplicationContextlnitializedEvent->加载sources到context->发送ApplicationPreparedEvent->刷新上下文->计时器停止计时->发送ApplicationStartedEvent->调用框架启动扩展类->发送ApplicationReadyEvent

#### ·自动化装配

框架自动化装配步骤:收集配置文件中的配置工厂类、加载组件工厂、注册组件内定义bean
