### 接口设计

#### 入库扫描接口

1. 获取现场组盘信息
2. 建立固废、容器、库位及库的绑定关系

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-get-in`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|store_label_code|true|string|仓库标签编码|
|position_label_code|true|string|库位标签编码|
|container_label_code|true|string|容器标签编码|
|label_code|true|string|固废标签编码|

返回结果
```
{
    "code": 200,
    "content": "操作成功",
    "data": [
        {
            "opera_in_id": "015625cb6db18a8afbb45624acc80403",
            "transfer_detail_id": "015611416d2d8a8afbb455dd19da1bbf",
            "store_label_code": "LIB-Y-001",
            "position_label_code": "LSL-Y-001-001",
            "container_label_code": "CON-T-Y-001-001",
            "label_code": "HW42-Y1607220175",
            "total_weight": 0,
            "weight": null,
            "status": "1",
            "waste_name": "废氯苯",
            "category_code": "261-148-42",
            "produce_source": "正常生产过程产生",
            "harmful_ingredient": "苯",
            "package_type": "袋装",
            "is_key_waste": ""
        },
        ...
    ],
    "status": 200
}
```

关于错误返回值，参见错误说明

***

#### 解除固废绑定关系接口

解除固废与容器、库位及库的绑定关系

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-get-in/relieve`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|label_code|true|string|固废标签编码|

返回结果
```
{
    "code": 200,
    "content": "解除组盘成功"
}
```

关于错误返回值，参见错误说明

***

#### 退回固废接口

退回当前固废

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-get-in/back`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|transfer_detail_id|true|string|转移明细id|
|back_reason_index|true|string|退回原因索引|
|back_reason|true|string|退回原因|
|status|true|string|状态|

返回结果
```
{
    "code": 200,
    "content": "退回成功"
}
```

关于错误返回值，参见错误说明

***

#### 固废入库确认接口

将组盘、称重信息提交保存

URL `http://eadqas.whchem.com:8080/hwms/api/mobile-get-in/weight`

支持格式 `JSON`

HTTP请求方式 `POST`

请求参数

|参数|必选|类型及范围|说明|
|-|-|-|-|
|store_label_code|true|string|仓库标签编码|
|position_label_code|true|string|库位标签编码|
|container_label_code|true|string|容器标签编码|
|list|true|list|固废详情列表|

返回结果
```
{
    "type": "warning",
    "content": "固废：HW42-Y1607220175，正确入库：LIB-Y-003;",
    "code": 200
}
```

关于错误返回值，参见错误说明
