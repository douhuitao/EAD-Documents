### 功能模块调用时序图

EAD 引擎模块调用顺序如下图所示：

![PNG](..\images\7.png)

#### 1. Spring Boot

客户端发起请求后，经过 Spring Boot 处理，进行路由层；

#### 2. Router layer

从Spring Boot 传递的请求，到路由层。
路由层分为三个模块进行请求处理；

- 应用入口（AppController）;
- 通用路由（SysController），包括用户登录、用户退出登录、修改密码，切换角色等;
- 资源路由（MainController），负责所有资源请求的处理；

#### 3. ViewFactory；

路由把当前应用会话信息传递至视图工厂，由视图工厂实例化视图；

#### 4. ActionFactory

若当前进行视图数据操作，则进入视图动作工厂， 由视图动作工厂进行操作处理；

#### 5. Render

请求处理完成后，进入 Render，由 Render 负责结果渲染输出。


