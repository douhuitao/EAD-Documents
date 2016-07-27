### 接口设计

#### 获取出库转移单接口

刷车卡获取当前车卡绑定的出库转移单

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwot/record`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|card_id|true|string|车卡号|

返回结果
```
{
    "data": [
        {
            "apply_code": "201607220008",
            "car_code": "鲁F67930",
            "card_code": "6ffa66cd",
            "card_id": "6ffa66cd",
            "card_name": "车卡#2",
            "user_name": "刘广安",
            "dispose_enterprise_name": "鑫广绿环再生资源股份有限公司",
            "duty_person": "刘广安",
            "five_bills_code": "11111",
            "lock_code": "LOCK-001",
            "org_name": "水系统",
            "parent_org_name": "UT装置",
            "phone": "11111",
            "transfer_id": "015611375ab88a8afbb455dd19da1b9c",
            "transfer_enterprise_name": "鑫广绿环再生资源股份有限公司",
            "plan_transfer_time": 1469167500000,
            "create_time": 1469167655558
        },
        ...
    ],
    "content": "操作成功",
    "code": 200
}
```

关于错误返回值，参见错误说明

***

#### 获取出库转移明细接口

获取出库转移明细

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-out-store`

支持格式 `JSON`

HTTP请求方式 `GET`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|transfer_id|true|string|出库转移单id|

返回结果
```
{
    "data": {
        "collection": [
            {
                "label_code": "CON-T-Y-001-001",
                "object_name": "001-001",
                "out_record_id": "01561fab9fc18a8afbb3561c80c200c6",
                "out_type": "CON"
            },
            ...
        ]
    },
    "type": "standard",
    "code": 0
}
```

关于错误返回值，参见错误说明

***

#### 扫描查询接口

查询当前扫描到的仓库(库位、容器、固废)标签下存在的固废

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-get-in`

支持格式 `JSON`

HTTP请求方式 `GET`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|store_label_code|false|string|仓库标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|position_label_code|false|string|库位标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|container_label_code|false|string|容器标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|label_code|false|string|固废标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|status|true|int|状态|

返回结果
```
{
    "data": {
        "collection": [
            {
                "category_code": "261-146-42",
                "container_label_code": "CON-T-Y-001-002",
                "label_code": "HW42-Y1607220173",
                "parent_category_code": "HW42",
                "position_label_code": "LSL-Y-001-002",
                "store_label_code": "LIB-Y-001",
                "waste_name": "实验室有机废液",
                "weight": "100"
            },
            ...
        ]
    },
    "type": "standard",
    "code": 0
}
```

关于错误返回值，参见错误说明

***

#### 固废出库添加接口

将当前固废加入到出库申请明细中

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-out-store`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|label_code|false|string|仓库(库位、容器、固废)标签编码|
|transfer_id|true|string|出库转移单id|

返回结果
```
{
    "content": "操作成功",
    "code": 200
}
```

关于错误返回值，参见错误说明

***

#### 点击查询接口

点击列表中的仓库(库位、容器、固废)查询当前包含的固废信息

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-get-out`

支持格式 `JSON`

HTTP请求方式 `GET`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|store_label_code|false|string|仓库标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|position_label_code|false|string|库位标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|container_label_code|false|string|容器标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|label_code|false|string|固废标签编码,仓库、库位、容器、固废标签编码必须有且只有一个存在|
|out_record_id|true|string|出库记录id|

返回结果
```
{
    "data": {
        "collection": [
            {
                "container_label_code": "CON-T-Y-001-002",
                "label_code": "HW42-Y1607220170",
                "position_label_code": "LSL-Y-001-002",
                "store_label_code": "LIB-Y-001",
                "waste_name": "实验室有机废液"
            },
            ...
        ]
    },
    "type": "standard",
    "code": 0
}
```

关于错误返回值，参见错误说明

***

#### 移除固废接口

将当前固废从出库申请明细中移除

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-out-store/remove`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|out_record_id|true|string|出库转移单id|

返回结果
```
{
    "content": "操作成功",
    "code": 200
}
```

关于错误返回值，参见错误说明

***

#### 出库转移单完成接口

将当前出库转移单标记为完成状态

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwot/finish`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|card_id|true|string|车卡号|
|transfer_id|true|string|出库转移单id|

返回结果
```
{
    "content": "操作成功",
    "code": 200
}
```

关于错误返回值，参见错误说明
