### 接口设计

#### 获取转移单接口

获取装车确认(内部转移)单，登录成功后加载主页时、同步转移单成功后调用

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwit`

支持格式 `JSON`

HTTP请求方式 `GET`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|card_id|true|string|登录人(车)卡号|

返回结果
```
{
    "data": {
        "collection": [
            {
                "transfer_id": "01561140fc788a8afbb455dd19da1bbc",
                "apply_code": "201607220009",
                "org_name": "PDH反应",
                "parent_org_name": "丙烷脱氢装置",
                "apply_date": 1469116800000,
                "transfer_type": "inner",
                "phone": "11111",
                "duty_person": "刘广安",
                "create_time": 1469168286787,
                "detail_status": "-1",
                "operator": "rmyin",
                "detail": [
                    {
                        "transfer_detail_id": "015611416d678a8afbb455dd19da1bc9",
                        "transfer_id": "01561140fc788a8afbb455dd19da1bbc",
                        "waste_detail_id": "015611404c0d8a8afbb455dd19da1bba",
                        "waste_name": "废氯苯",
                        "category_code": "261-148-42",
                        "harmful_ingredient": "苯",
                        "is_key_waste": "",
                        "package_type": "袋装",
                        "label_code": "HW42-Y1607220185",
                        "container_label_code": "",
                        "status": "wait",
                        "create_time": 1469168315627
                    },
                    ...
                ]
            },
            ...
        ]
    }
}
```

关于错误返回值，参见错误说明

***

#### 转移单同步接口

同步装车确认(内部转移)单

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwit/sync`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|缓存数据|true|string|缓存的转移单及详情数据|

示例
```
[
    {
        "apply_code": "201607220009",
        "transfer_type": "inner",
        "detail": [
            {
                "category_code": "261-148-42",
                "container_label_code": "",
                "harmful_ingredient": "苯",
                "is_key_waste": "",
                "label_code": "HW42-Y1607220185",
                "package_type": "袋装",
                "status": "pass",
                "transfer_detail_id": "015611416d678a8afbb455dd19da1bc9",
                "transfer_time": "2016-07-26 14:03:57",
                "waste_detail_id": "015611404c0d8a8afbb455dd19da1bba",
                "waste_name": "废氯苯"
            },
            ...
        ]
    },
    ...
]
```

返回结果
```
{
    "code": 200,
    "content": "同步成功",
    "data": null,
    "error": null,
    "exception": null,
    "redirect": null,
    "status": 200,
    "type": null
}
```

关于错误返回值，参见错误说明
