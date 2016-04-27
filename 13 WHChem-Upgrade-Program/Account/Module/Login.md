## Portal 单点登录

![LDAP 认证](../../images/portal-sign-in.png)

Portal 单点登录流程：
0. Portal 重定向或超链接到 EAD 平台;
- 调用 LTPA 认证模块判断用户是否在 Portal 已经登录;
- LTAP 安全校验成功后根据返回的用户 ID 执行自动登录;
- LTPA 判断没有 Portal 登录信息或自动登录成功后进入 EAD 平台 Session 模块;
- Session 认证模块判断权限;
- Session 认证模块判断成功后进入业务视图;
- Session 认证模块判断失败切换到 EAD 登录窗口（EAD 登录窗口 包含链接到 Portal 登录界面的提示信息）;

### LTPA 配置参数

**密码：** Password
**安全密钥：** 3DESKey
