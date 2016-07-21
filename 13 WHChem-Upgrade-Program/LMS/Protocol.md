## 接口及协议

![协议](../images/lms-integrated.png)

固废管理系统采用标准的 Rest API 通过 PI 向物流系统请求或提供接口服务。PI 将固废管理系统的 Rest API 适配转换为物流管理系统对应的接口协议进行转发处理。

### 字符集编码

UTF-8

### 安全认证

EAD 物流系统接口账号和密码验证。

### 响应消息

#### 成功

```
{
    "code": "success",
    "content": "",
    "data": {

    },
    "status":"200"
}
```

#### 失败

```
{
    "code": "error",
    "content": "错误消息内容",
    "status":"400"
}
```

### PI 转换

PI 根据物流系统可以提供的接口协议进行相应的映射配置。

## 固废外运车卡信息同步（激活、更新、注销）

### 类型

- 方式：POST
- 主动通过 PI 向物料系统发起 POST 请求。

### 请求参数

|属性|名称|类型|备注|
|---|---|---|---|
|card_id|车卡 ID|String(48)|NFC 卡 ID|
|apply_code|业务单号|String(64)|固废系统外运处置单号。|
|car_number|车牌号|String(64)|运输车辆牌照号码|
|region|区域编码|String(64)|固废系统，区域编码，烟台：YT，宁波：NB 。|
|goods_name|货物名称|String(64)|固废名称|
|ship_enterprise|发货单位|String(64)|发货单位名称|
|dispose_enterprise|接受单位|String(64)|接收单位名称|
|status|车卡状态|String(64)|1：有效，0：无效|

### 参数示例

```
{
    "card_id":"39092d65",
    "apply_code":"201607140049",
    "car_number":"鲁F68601",
    "goods_name":"废 MDI",
    "ship_enterprise":"烟台工业园指挥部",
    "dispose_enterprise":"鑫广绿环再生资源股份有限公司",
    "region":"YT",
    "status":"1"
}
```

向 PI 以 POST 方式通过 JSON Body 发送数据项。


## 固废外运车辆过磅数据同步

### 类型

- 方式：PUT
- 提供接口供 PI 以 PUT 方式调用。

### 请求参数

物流系统通过 PI 以 PUT 方式通过 JSON Body 发送数据项。

|属性|名称|类型|备注|
|---|---|---|---|
|card_id|车卡 ID|String(48)|NFC 卡 ID|
|apply_code|业务单号|String(64)|固废系统外运处置单号。|
|car_number|车牌号|String(64)|运输车辆牌照号码|
|tare_weight|皮重|Int|单位：千克|
|gross_weight|毛重|Int|单位：千克|
|net_weight|净重|Int|单位：千克|
|first_time|空车过磅时间|Datetime|格式：2016-01-01 12:00:00|
|first_node|空车过磅点|String(64)|空车过磅点标识|
|second_time|重车过磅时间|Datetime|格式：2016-01-01 12:00:00|
|second_node|重车过磅点|String(64)|空车过磅点标识|
|image_url|过磅监控截图 URL|String(1024)|多个图片用英文逗号 “,” 分隔|

### 参数示例

```
{
    "card_id":"39092d65",
    "apply_code":"201607140049",
    "car_number":"鲁F68601",
    "tare_weight":"100000",
    "gross_weight":"300000",
    "net_weight":"200000",
    "first_time":"2016-07-14 10:00:35",
    "first_node":"4号门-1号磅",
    "second_time":"2016-07-14 14:00:55",
    "second_node":"4号门-2号磅",
    "image_url":"/web/images/12057898.jpg,/web/images/12057899.jpg"
}
```


