## BPM 集成方案

### 概述

EAD 平台与万华化学集团现有 BPM 系统进行集成，实现 EAD 平台可以通过配置开发通用支持 BPM 工作流引擎，实现 EAD 平台应用跨平台协同办公的需求，分别对 EAD 平台和 BPM 进行扩展升级。本章描述本次集成升级的方式、流程以及 EAD 引擎、Rainbow 和 BPM 升级开发的协议和具体功能实现。

### 集成应用场景

![BPM 集成](../images/bpm-integrated.png)

EAD 平台与 BPM 的集成应用场景主要分为 EAD 平台发起和 BPM 发起两种应用场景。

#### EAD 平台发起
用户通过 EAD 平台发起工作流相关操作，EAD 引擎通过扩展驱动以 Rest 协议的方式与 BPM Rest API 进行集成和交互。

#### BPM 平台发起
用户通过 BPM 待办列表链接方式重定向或打开 EAD 相关业务表单详情视图。EAD 前端引擎 Rainbow 利用 Ajax 异步请求 EAD 引擎获取视图渲染元数据，EAD 引擎通过扩展驱动以 Rest 协议的方式与 BPM Rest API 进行集成和交互。

### 集成流程

![BPM 集成](../images/bpm-process.png)

本次集成升级分别包括 Rainbow、EAD Engine、BPM 三层，在 EAD 平台主要通过扩展开发 BPM 相关的事件扩展驱动和 EAD 引擎视图扩展和视图动作扩展驱动，通过 EAD 配置开发工具定义和配置构建 BPM 相关业务视图。
