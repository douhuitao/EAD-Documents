### APIs

EAD 引擎除与 Rainbow 前端引擎的接口外，还有自身提供的一些对外交互的 API。

### 单点登录

平台本身提供了单点登录功能，第三方系统通过与该接口的对接，实现从平台应用登录到第三方应用。
实现单点登录在平台中进行简单配置，配置方法如下：
在开发者中心应用中：配置 —> 系统变量
- 配置第三方应用地址：`{appName}-login-app`，例如：`monitor-login-app`
- 配置第三方应用appKey：`{appName}-login-key`，例如：`monitor-login-key`

调用方法：

请求URL：/{appName}/api/login-app，如：/monitor/api/login-app
Method：Get
参数传入：
- token：66a98e0de29e7556957a9a180eb2d1fa
- userId=admin
- time=1458718466027

Token 生成规则：MD5(account + time + appKey)


