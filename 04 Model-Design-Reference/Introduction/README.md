### 1. 概述

#### 数据类型映射

| EAD 数据类型 | 类型说明 | Mysql 数据类型 |
| ---------- | ------- | ------------- |
| alpha | 字母 | varchar(512) |
| alphanumeicunline | 字母数字下划线 |varchar(512) |
| alphanumeric | 字母数字 | varchar(512) |
| array | 数组 | text |
| bin | 二进制 | blob |
| bool | 布尔型 | tinyint(1) |
| collection | 集合 | char(48) | 
| date | 日期 | bigint(20) |
| datetime | 日期 | Date |
| email | Email | varchar(512) |
| file | 文件 | varchar(512) |
| geopoint | 地理坐标 | text |
| html | HTML | text |
| id | ID | char(48) |
| image | 图片 | varchar(512) |
| integer | 整型 | bigint(20) |
| list | 列表 | text |
| model | 模型 | char(48) |
| month | 月 | bigint(20) |
| number | 数字 | float(15,2) |
| object | 对象 | text |
| password | 密码 | varchar(512) |
| string  | 长字符串 | varchar(512) |
| text  | 文本 | text|
| time  | 时间 | bigint(20) |
| token  | 令牌 | varchar(512) |
| url | URL | varchar(512) |
| uuid | UUID | char(48) |
| variable | 变量 | varchar(512) |
| week | 周 | bigint(20) |
| wordbook | 字典 | char(48) |
| year | 年 | bigint(20) |