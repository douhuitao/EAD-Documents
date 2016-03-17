### 2. BASE Model

模板模型，在设计模型时若是特定功能模型，请继承相关模型。

#### 1、网盘基础结构 ($box_node)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| node_id | 节点主键 | uuid | 是 | - | - | - | 1 | 
| node_pid | 父节点主键 | id | 否 | - | - | - | - | 
| node_name | 节点名称 | string | 是 | - | - | - | - | 
| source_name | 节点源名称 | string | 否 | - | - | - | - | 
| location | 节点路径 | string | 否 | - | - | - | - | 
| path_info | 路径信息 | text | 否 | - | - | - | - | 
| node_depth | 节点深度 | string | 否 | - | - | - | - | 
| child_num | 子节点数 | string | 否 | - | - | - | - | 
| category | 分类 | string | 否 | - | - | - | - | 
| node_info | 节点信息 | text | 否 | - | - | - | - | 
| node_setting | 节点设置 | text | 否 | - | - | - | - | 
| file_ext | 扩展名 | string | 否 | - | - | - | - | 
| file_size | 文件长度 | string | 否 | - | - | - | - | 
| preview_status | 预览状态 | string | 否 | - | - | - | - | 
| reference_node | 引用节点 | string | 否 | - | - | - | - | 
| link_url | 链接地址 | text | 否 | - | - | - | - | 
| note | 备注 | string | 否 | - | - | - | - | 
| data_status | 数据状态 | string | 否 | - | - | normal | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 

#### 2、文件列表模板 ($document)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| node_id | 主键 | uuid | 是 | - | - | - | 1 | 
| node_name | 节点名称 | string | 否 | - | - | - | - | 
| parent_id | 父节点 | id | 否 | - | - | - | - | 

#### 3、文件模板 ($file_list)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| file_id | File ID | uuid | 是 | - | - | - | 1 | 
| file_name | File Name | string | 是 | - | - | - | - | 
| file_type | File Type | string | 否 | - | - | - | - | 
| file_ext | File Extend | string | 否 | - | - | - | - | 
| file_size | File Size | integer | 否 | - | - | - | - | 
| md5_hash | File MD5 Hash | string | 否 | - | - | - | - | 
| upload_time | Upload Time | time | 否 | - | - | - | - | 
| create_time | Create Time | time | 否 | - | - | ${time} | - | 
| update_time | Update Time | time | 否 | - | - | ${time} | - | 
| file | File | id | 否 | - | - | - | - | 
| object_id | Object ID | id | 否 | - | - | - | - | 

#### 4、日程模板 ($schedule)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| start_time | 开始时间 | time | 否 | - | - | - | - | 
| end_time | 结束时间 | time | 否 | - | - | - | - | 

#### 5、简单数据模板 ($simple_data)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| uuid | 主键 | uuid | 是 | - | - | - | 1 | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 

#### 6、标准数据模板 ($standard_data)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| uuid | 主键 | uuid | 是 | - | - | - | 1 | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 
| updator | 更新者 | id | 否 | - | - | ${uid} | - | 

#### 7、工作流模板 ($workflow)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| bridge_id | 适配器主键 | uuid | 否 | - | - | - | - | 
| case_id | 实例主键 | id | 否 | - | - | - | - | 
| data_id | 数据主键 | id | 否 | - | - | - | - | 
| uid | 操作者 | id | 否 | - | - | - | - | 
| flow_object | 工作流对象 | text | 否 | - | - | - | - | 
| flow_create_time | 流程创建时间 | time | 否 | - | - | - | - | 
| flow_update_time | 流程更新时间 | time | 否 | - | - | - | - | 
| flow_status | 流程状态 | string | 否 | - | - | - | - | 