### 接口设计

#### 登录接口

使用帐号密码登录系统

URL `http://eadqas.whchem.com:8080/hwms/api/mobile/login`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|userId|true|string|登录人帐号|
|password|true|string|登录人密码|

返回结果
```
{
    "code": 200,
    "content": "登录成功",
    "data": {
        "card_id": "2f322985",
        "card_code": "2f322985",
        "card_name": "员工卡#1",
        "type": "person",
        "uid": "clxie",
        "account": "clxie",
        "user_name": "解春柳",
        "role_name": "固废系统开发组",
        "role_code": "hwms-developer",
        "role_mobile_res": "装车确认,内部转移,固废入库,内部利用,固废出库"
    },
    "status": 200
}
```

关于错误返回值，参见错误说明

***

#### 卡同步接口

获取当前可登录系统的员工(车)卡信息，程序打开时调用

URL `http://eadqas.whchem.com:8080/hwms/api/card/sync`

支持格式 `JSON`

HTTP请求方式 `GET`

请求参数 `无`

返回结果
```
{
    "code": 200,
    "content": "同步成功",
    "data": [
        {
            "card_id": "2f322985",
            "card_code": "2f322985",
            "card_name": "员工卡#1",
            "type": "person",
            "uid": "clxie",
            "account": "clxie",
            "user_name": "解春柳",
            "role_name": "固废系统开发组",
            "role_code": "hwms-developer",
            "role_mobile_res": "装车确认,内部转移,固废入库,内部利用,固废出库"
        },
        ...
    ],
    "status": 200
}
```

关于错误返回值，参见错误说明
