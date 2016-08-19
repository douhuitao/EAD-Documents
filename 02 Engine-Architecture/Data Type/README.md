### 数据类型

EAD 平台数据类型是由**元数据类型**与**基础数据类型**组成，所有基础数据类型都基于元类型组成。

元类型及元类型所对应的Java数据类型、Mysql数据类型、SQL Server数据类型、Oracle数据类型映射关系如下：

元类型 | Java Data Type | Mysql | SQL Server | Oracle | 说明
----- | -------------- | ----- | ---------- | ------ | 
Key | String | char(48) | char(48) | varchar2(48) | 键值，使用于主外键
Boolean | boolean | tinyint(1) | bit | number(1) | Boolean类型
String | String | varchar | varchar | varchar2 | 字符串类型，默认为64，可以在模型属性中增大其长度
Text | String | mediumtext | text | clob | 文本类型
Integer | long | bigint(20) | bigint | number(20) | 整形
Number | double | double | double | double | 浮点型，精度根据业务需求在数据库中进行设置
Time | long | bigint(20) | bigint | number(20) | EAD平台使用的时间型，保存时间戳
Object | String | mediumtext | text | clob | 对象类型
Array | String | mediumtext | text | clob | 数组类型
Binary | byte[] | blob | blob | blob | 二进制型
DateTime | String | Date | Date | Date | 数据库日期型

> 注意：Number类型使用Double类型，精度根据业务需求在数据库中进行设置，若不设置精度，则在具体业务计算中需要进行精度处理。