### 主要配置文件说明

#### gbros-root 工程

- gbros-root/pom.xml: Maven 打包配置文件，定义了包依赖关系；

#### gbros-hill 工程

- gbros-hill/pom.xml: Maven 打包配置文件，定义了包依赖关系；
- gbros-hill/src/main/resource/spring-ead.xml: 引擎相关 Spring 配置文件
- gbros-hill/src/main/resource/mybatis/*: 核心配置模块与系统管理模块 mybatis 相关配置文件

#### gbros-web 工程

- gbros-web/pom.xml: Maven 打包配置文件，定义了包依赖关系；
- gbros-web/src/main/resource/application.properties: EAD 平台 Spring 配置文件；
- gbros-web/src/main/resource/log4j.properties: Log4j 日志配置；
- gbros-web/src/main/resource/spring.xml: EAD 平台 Spring 配置文件；
- gbros-hill/src/main/resource/properties/app.properties: 引擎配置文件，定义数据类型映射；
- gbros-web/src/main/resource/datasource/jdbc.properties: 核心配置库与系统库 Mysql 数据连接配置；
- gbros-web/src/main/resource/datasource/mongo.properties: 存储库 Mongodb 连接配置；
- gbros-web/src/main/resource/i18n/*: 国际化及多语言配置；
- gbros-web/src/main/resource/statis/*: 前端文件；
