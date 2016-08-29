# EAD 安装部署手册

本文档为 EAD 平台的安装部署手册，包括依赖软件的安装及平台本身的部署。

## 依赖软件安装

### Mysql 安装

平台依赖 Mysql 数据库，用于存放**核心配置数据**及**系统管理数据**。
详细配置安装见本手册：`服务器运行环境准备 - > Winows Server -> 安装 Mysql`

### Mongodb 安装

平台依赖 Mongodb 数据库，使用 GridFS 存储文件。
详细配置安装见本手册：`服务器运行环境准备 - > Winows Server -> 安装 Mongodb`

### Tomcat 安装

平台运行时依赖 Tomcat Web 容器。
详细配置安装见本手册：`服务器运行环境准备 - > Winows Server -> 安装 Tomcat`

## 平台部署

依赖软件安装完成后，按以下步骤进行平台部署：

第一步：初始化配置数据，即：导入平台所依赖的**核心配置数据（ead库）**与**系统库（sys）**；
第二步：配置 Tomcat，拷贝应用至 Tomcat 容器中；
第三步：启动 Tomcat Web 容器。



