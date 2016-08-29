### 接口设计

#### 获取内部利用转移单接口

获取内部利用转移单

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwiu`

支持格式 `JSON`

HTTP请求方式 `GET`

请求参数 `无`

返回结果
```
{
    "data": {
        "collection": [
            {
                "apply_code": "201607250001",
                "user_name": "陶林",
                "inner_id": "0156209318738a8afbb4561c820000a5",
                "org_name": "烟台水性装置",
                "parent_org_name": "表面材料事业部",
                "phone": "18153510000",
                "create_time": 1469425326134
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

#### 获取内部利用转移明细接口

获取内部利用转移明细

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwiu/{inner_id}/detail`

支持格式 `JSON`

HTTP请求方式 `GET`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|inner_id|true|string|内部利用转移单id|

返回结果
```
{
    "data": {
        "collection": [
            {
                "category_code": "900-015-08",
                "harmful_ingredient": "甲醇",
                "is_key_waste": "0",
                "label_code": "HW08-Y1607140002",
                "package_type": "袋装",
                "produce_source": "正常生产过程产生",
                "record_id": "0155e7e6c3a58a8afbb355dd18c20c97",
                "waste_name": "长链烷烃脱氢过程产生的废催化剂"
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

#### 扫描添加固废接口

将扫描的固废加入到内部利用申请明细中

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwiu/{inner_id}/detail`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|inner_id|true|string|内部利用转移单id|
|label_code|true|string|固废标签编码|

返回结果
```
{
    "data": {
        "category_code": "900-015-08",
        "harmful_ingredient": "甲醇",
        "is_key_waste": "0",
        "label_code": "HW08-y1607140002",
        "package_type": "袋装",
        "produce_source": "正常生产过程产生",
        "record_id": "01562635863f8a8afbb45624acc80478",
        "waste_name": "长链烷烃脱氢过程产生的废催化剂"
    },
    "content": "操作成功",
    "code": 200
}
```

关于错误返回值，参见错误说明

***

#### 移除固废接口

将当前固废从内部利用申请明细中移除

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwiu/{inner_id}/detail/remove`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|inner_id|true|string|内部利用转移单id|
|label_code|true|string|固废标签编码|

返回结果
```
{
    "content": "操作成功",
    "code": 200
}
```

关于错误返回值，参见错误说明

***

#### 内部利用转移单完成接口

将当前内部利用转移单标记为完成状态

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-hwiu/finish`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|inner_id|true|string|内部利用转移单id|

返回结果
```
{
    "content": "操作成功",
    "code": 200
}
```

关于错误返回值，参见错误说明
