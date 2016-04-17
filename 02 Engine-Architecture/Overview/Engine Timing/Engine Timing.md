### 引擎时序总图

平台引擎模块调用顺序如下图所示：

![PNG](..\..\images\8.png)

#### 1. 客户端（Client）

客户端发起请求，进入路由，由路由模块进行请求分发；

#### 2. 中间件（Middleware）

Router : 

1、路由根据请求的API的不同，分发不同的路由：
 
 - 应用入口API
 - 系统级API
 - 视图及视图动作请求API

 2、接受 RenderFactory 渲染内容进行输出；

Render Factory:渲染输出请求返回内容；

- FileRender
- HtmlRender
- InlineRender
- JavaScriptRender
- JsonRender
- MessageRender
- TextRender

#### 3. 引擎核心（Engine）

View Factory：

视图及视图动作由路由分发至ViewFactory，在ViewFactory中实例化视图，包括加入Schema，由QueryFactory提供数据内容，若请求为视图动作，则交由视图动作工厂进行处理；

Query Factory:

查询工厂实例化查询后，由查询为视图提供数据内容；

Action Factory:

视图动作工厂接收视图的处理请求，对操作进行处理，包括新增数据、修改数据、删除数据或其他特殊操作；

#### 4. 数据交互（Data）

Model(ORM):

ORM 为查询与视图动作提供底层数据操作接口，通过ORM，可以从数据库中获取数据或操作数据库中的数据；

Storage:

存储功能为视图动作提供文件存储能力；

#### 5. 功能模块（Modules）

EngineConfig：

由于EAD引擎是基于配置的进行开发的，所以需要由配置模块为引擎提供配置数据；

Notice:

通知模块可以在视图动作中进行调用，提供通知能力；

Others:


