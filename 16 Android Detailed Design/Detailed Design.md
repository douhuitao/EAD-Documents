# 详细设计

### 接口说明

应用涉及到的所有接口使用同一的接口认证方式和统一的异常处理方式，这里统一说明

#### 接口认证

接口认证采用用户帐号、时间戳、密钥组合加密方式认证，所有接口的认证信息都在请求报头中体现

支持格式 `JSON`

HTTP请求方式 `POST` `GET` `PUT` `DELETE`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|userId|true|string|登录人帐号(卡同步接口和帐号密码登录接口可传null)|
|time|true|string|当前时刻的Unix时间戳|
|token|true|string|userId、time和密钥经过md5加密生成|

示例
```
{
    "userId": "clxie",
    "time": "1469607566",
    "token": "5ece831702283ec26aa690a0bba214a3"
}
```

#### 错误说明

所有接口返异常的方式如下

支持格式 `JSON`

示例
```
{
    "code": 500,
    "content": "认证异常，请检查设备时间或与管理员联系",
    "error": "ERROR_AUTH_FAILED",
    "type": "failed"
}
```

返回结果说明

|参数|类型及范围|说明|
|-|-|-|
|code|int|错误代码|
|content|string|错误详情|
|error|string|错误说明|
|type|string|类型|
