## SYS

系统模型

### 1、账户 (sys_account)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| uid | 用户主键 | uuid | 否 | - | - | - | - | 
| account | 账号 | alphanumeric | 是 | - | - | - | 1 | 
| account_code | 编号 | alphanumeric | 否 | - | - | - | - | 
| password | 密码 | password | 否 | - | - | - | - | 
| email | 邮箱 | email | 否 | - | - | - | - | 
| phone | 手机 | string | 否 | - | - | - | - | 
| salt | 安全加盐 | token | 否 | - | - | - | - | 
| user_type | 用户类型 | string | 否 | - | - | - | - | 
| register_time | 注册时间 | time | 否 | - | - | - | - | 
| last_active_time | 最后活动时间 | time | 否 | - | - | - | - | 
| last_login_time | 最后登录时间 | time | 否 | - | - | - | - | 
| account_status | 账户状态 | string | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| role | 角色 | sys_role | 否 | - | - | - | - | 
| user_name | 用户名称 | string | 否 | - | - | - | - | 
| contacts_title | 用户头衔 | string | 否 | - | - | - | - | 
| abbreviation | 简称 | string | 否 | - | - | - | - | 
| contacts_alias | 别名 | string | 否 | - | - | - | - | 
| org_id | 组织 | wordbook | 否 | - | - | - | - | 
| address | 地址 | string | 否 | - | - | - | - | 

### 2、联系人账户 (sys_account_contacts)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| uid | 用户主键 | uuid | 否 | - | - | - | - | 
| account | 账户 | string | 否 | - | - | - | - | 
| user_name | 用户名 | string | 否 | - | - | - | - | 
| role_id | Role | id | 否 | - | - | - | - | 
| role_name | Role Name | string | 否 | - | - | - | - | 
| role_code | Role Code | string | 否 | - | - | - | - | 

### 3、用户角色 (sys_account_role)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| relation_id | 关系主键 | uuid | 是 | - | - | - | 1 | 
| uid | 用户主键 | wordbook | 是 | - | - | - | - | 
| role_id | 角色主键 | wordbook | 是 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 
| is_default | 是否默认 | bool | 否 | - | - | - | - | 
| account | 账号 | string | 否 | - | - | - | - | 

### 4、系统动态 (sys_activity)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| activity_id | 主键 | uuid | 否 | - | - | - | - | 
| activity_actor | 操作者 | wordbook | 否 | - | - | - | - | 
| role_id | 角色 | wordbook | 否 | - | - | - | - | 
| app_id | 应用 | wordbook | 否 | - | - | - | - | 
| res_id | 资源 | wordbook | 否 | - | - | - | - | 
| action_id | 操作 | wordbook | 否 | - | - | - | - | 
| view_id | 视图 | wordbook | 否 | - | - | - | - | 
| data_id | 数据 | id | 否 | - | - | - | - | 
| action_type | 动作类型 | string | 否 | - | - | - | - | 
| activity_content | 动态内容 | string | 否 | - | - | - | - | 
| before_data | 操作前数据 | text | 否 | - | - | - | - | 
| after_data | 操作后数据 | text | 否 | - | - | - | - | 
| activity_path | 路径 | string | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 
| activity_actor_account | 操作账户 | string | 否 | - | - | - | - | 
| activity_actor_name | 操作者名称 | string | 否 | - | - | - | - | 
| role_name | 角色 | string | 否 | - | - | - | - | 
| app_name | 应用 | string | 否 | - | - | - | - | 
| res_name | 资源 | string | 否 | - | - | - | - | 
| action_name | 操作 | string | 否 | - | - | - | - | 
| view_name | 视图 | string | 否 | - | - | - | - | 
| node_id | 节点 | id | 否 | - | - | - | - | 

### 5、网盘权限 (sys_box_competence)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| competence_id | 权限主键 | uuid | 是 | - | - | - | 1 | 
| node_id | 节点主键 | id | 是 | - | - | - | - | 
| uid | 用户主键 | id | 是 | - | - | - | - | 
| competence_type | 权限类型 | string | 否 | - | - | - | - | 
| is_inherit | 是否继承 | bool | 否 | - | - | - | - | 

### 6、网盘自定义视图 (sys_box_custom_view)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| view_id | 视图主键 | uuid | 是 | - | - | - | 1 | 
| view_name | 视图名称 | string | 否 | - | - | - | - | 
| view_type | 视图类型 | string | 否 | - | - | - | - | 
| view_title | 视图标题 | string | 否 | - | - | - | - | 
| view_structure | 视图结构 | string | 否 | - | - | - | - | 
| html_fragment | HTML片段 | string | 否 | - | - | - | - | 
| data_status | 数据状态 | string | 否 | - | - | normal | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| invalid_time | 失效时间 | time | 否 | - | - | - | - | 
| create_user | 创建用户 | string | 否 | - | - | ${uid} | - | 

### 7、网盘分享 (sys_box_share)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| share_id | 主键 | uuid | 是 | - | - | - | 1 | 
| view_id | 视图id | id | 否 | - | - | ${appKey} | - | 
| users | 分享对象 | string | 否 | - | - | - | - | 
| node_id | 节点主键 | id | 否 | - | - | - | - | 
| share_token | 分享令牌 | string | 否 | - | - | - | - | 
| password | 分享密码 | password | 否 | - | - | - | - | 
| is_inherit | 是否继承 | bool | 否 | - | - | - | - | 
| note | 备注 | string | 否 | - | - | - | - | 
| data_status | 数据状态 | string | 否 | - | - | normal | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| expire_time | 过期时间 | time | 否 | - | - | - | - | 
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 
| node_name | 资源名称 | string | 否 | - | - | - | - | 

### 8、联系人 (sys_contacts)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| contacts_id | 联系人主键 | uuid | 否 | - | - | - | - | 
| contacts_name | 联系人名称 | string | 是 | - | - | - | - | 
| contacts_title | 头衔 | string | 否 | - | - | - | - | 
| contacts_alias | 别名 | string | 否 | - | - | - | - | 
| abbreviation | 缩写 | string | 否 | - | - | - | - | 
| phone | 电话组 | string | 否 | - | - | - | - | 
| email | 邮件组 | email | 否 | - | - | - | - | 
| address | 地址组 | string | 否 | - | - | - | - | 
| uid | UID | wordbook | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 
| org_id | 组织 | wordbook | 否 | - | - | - | - | 

### 9、联系人角色 (sys_contacts_role)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| contacts_role_id | Contacts Role ID | uuid | 是 | - | - | - | - | 
| role_code | Role Code | string | 是 | - | - | - | - | 
| role_name | Role Name | string | 是 | - | - | - | - | 
| note | Note | text | 否 | - | - | - | - | 
| sort_num | Sort | integer | 否 | - | - | - | - | 
| status | Status | string | 否 | - | - | - | - | 
| create_time | Create Time | time | 否 | - | - | ${time} | - | 
| update_time | Update Time | time | 否 | - | - | ${time} | - | 
| creator | Creator | id | 否 | - | - | ${uid} | - | 
| role_type | Role Type | string | 是 | - | - | - | - | 

### 10、区域 (sys_district)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| district_id | 主键 | uuid | 是 | - | - | - | - | 
| district_code | 编码 | string | 否 | - | - | - | - | 
| district_cn_name | 行政区名称 | string | 是 | - | - | - | - | 
| district_alias | 别名 | string | 否 | - | - | - | - | 
| parent_district_id | 父级区域 | wordbook | 否 | - | - | - | - | 
| sort_num | 序号 | integer | 否 | - | - | - | - | 
| status | 状态 | string | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 

### 11、文档 (sys_document)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| doc_id | 视图主键 | uuid | 是 | - | - | - | 1 | 
| doc_name | 视图名称 | string | 是 | - | - | - | - | 
| doc_type | 视图类型 | string | 否 | - | - | - | - | 
| doc_title | 视图标题 | string | 否 | - | - | - | - | 
| keyword | 关键字 | string | 否 | - | - | - | - | 
| doc_status | 文档状态 | string | 否 | - | - | - | - | 
| data_status | 数据状态 | string | 否 | - | - | normal | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 
| summary | 摘要 | string | 否 | - | - | - | - | 
| thumbnail | 缩略图 | string | 否 | - | - | - | - | 
| data_type | 数据类型 | string | 否 | - | - | - | - | 
| meta_data | 元数据 | text | 否 | - | - | - | - | 
| raw_data | 原生数据 | text | 否 | - | - | - | - | 
| web_view | Web 视图 | text | 否 | - | - | - | - | 
| updator | 更新者 | string | 否 | - | - | - | - | 

### 12、收藏 (sys_favorite)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| favorite_id | 主键 | uuid | 是 | - | - | - | 1 | 
| view_id | 视图id | id | 否 | - | - | ${appKey} | - | 
| node_id | 节点主键 | id | 否 | - | - | - | - | 
| res_id | 资源主键 | id | 否 | - | - | - | - | 
| favorite_name | 收藏名称 | string | 是 | - | - | - | - | 
| click_num | 点击数量 | integer | 否 | - | - | - | - | 
| favorite_type | 收藏类型 | string | 否 | - | - | - | - | 
| note | 备注 | string | 否 | - | - | - | - | 
| data_status | 数据状态 | string | 否 | - | - | normal | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| invalid_time | 失效时间 | time | 否 | - | - | - | - | 
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 

### 13、文件记录 (sys_file)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| file_id | 文件主键 | uuid | 是 | - | - | - | 1 | 
| origin_id | 元主键 | string | 否 | - | - | - | - | 
| file_name | 文件名称 | string | 是 | - | - | - | - | 
| file_type | 文件类型 | string | 否 | - | - | - | - | 
| file_format | 文件规格 | string | 否 | - | - | - | - | 
| file_size | 文件长度 | string | 否 | - | - | - | - | 
| file_ext | 扩展名 | string | 否 | - | - | - | - | 
| mime_type | MIME类型 | string | 否 | - | - | - | - | 
| file_info | 文件信息 | text | 否 | - | - | - | - | 
| storage_engine | 存储引擎 | string | 否 | - | - | - | - | 
| file_key | 文件 | string | 否 | - | - | - | - | 
| file_source | 文件地址 | string | 否 | - | - | - | - | 
| storage_info | 存储信息 | text | 否 | - | - | - | - | 
| storage_type | 存储类型 | string | 否 | - | - | - | - | 
| md5_hash | MD5散列 | string | 否 | - | - | - | - | 
| document_id | 文档主键 | string | 否 | - | - | - | - | 
| action_id | 视图动作 | string | 否 | - | - | - | - | 
| file_status | 文件状态 | string | 否 | - | - | normal | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| invalid_time | 失效时间 | time | 否 | - | - | - | - | 
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 

### 14、工作流数据关系 (sys_flow_bridge)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| bridge_id | 主键 | uuid | 是 | - | - | - | 1 | 
| case_id | 实例 | wordbook | 是 | - | - | - | - | 
| data_id | 数据主键 | wordbook | 是 | - | - | - | - | 
| flow_object | 工作流对象 | text | 是 | - | - | - | - | 
| uid | 操作者 | id | 是 | - | - | - | - | 
| flow_create_time | 创建时间 | time | 是 | - | - | - | - | 
| flow_update_time | 修改时间 | time | 是 | - | - | - | - | 
| flow_status | 工作流状态 | string | 是 | - | - | - | - | 

### 15、系统日志 (sys_log)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| log_id | 日志主键 | uuid | 是 | - | - | - | - | 
| url | 请求URL | string | 是 | - | - | - | - | 
| session_id | 会话ID | string | 否 | - | - | - | - | 
| user_id | 当前用户 | wordbook | 否 | - | - | - | - | 
| brower | 浏览器 | string | 否 | - | - | - | - | 
| brower_version | 版本 | string | 否 | - | - | - | - | 
| user_agent | 客户端代理 | text | 否 | - | - | - | - | 
| ip | IP地址 | string | 否 | - | - | - | - | 
| os | 操作系统 | string | 否 | - | - | - | - | 
| screen_size | 屏幕分辨率 | string | 否 | - | - | - | - | 
| http_method | 请求方法 | string | 否 | - | - | - | - | 
| content_type | 内容类型 | string | 否 | - | - | - | - | 
| is_ajax | 是否AJAX请求 | bool | 否 | - | - | - | - | 
| request_time | 请求时间 | time | 否 | - | - | - | - | 
| response_time | 响应时间 | time | 否 | - | - | - | - | 
| device_type | 设备类型 | string | 否 | - | - | - | - | 
| header | HTTP头 | text | 否 | - | - | - | - | 
| cookie | Cookie | text | 否 | - | - | - | - | 
| operation_type | 操作类型 | string | 否 | - | - | - | - | 
| res_id | 资源 | id | 否 | - | - | - | - | 
| view_id | 视图 | wordbook | 否 | - | - | - | - | 
| action_id | 动作 | wordbook | 否 | - | - | - | - | 
| request_body | 请求内容 | text | 否 | - | - | - | - | 
| response_body | 响应内容 | text | 否 | - | - | - | - | 
| status_code | 状态编码 | string | 否 | - | - | - | - | 
| log_desc | 描述 | text | 否 | - | - | - | - | 
| app_id | App | wordbook | 否 | - | - | - | - | 

### 16、登录日志 (sys_login_log)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| log_id | 主键 | uuid | 是 | - | - | - | 1 | 
| uid | 用户主键 | id | 否 | - | - | - | - | 
| account | 登录账户 | string | 否 | - | - | - | - | 
| user_name | 名称 | string | 否 | - | - | - | - | 
| org_id | 组织 | id | 否 | - | - | - | - | 
| org_name | 组织名称 | string | 否 | - | - | - | - | 
| role_id | 角色ID | id | 否 | - | - | - | - | 
| role_name | 角色 | string | 否 | - | - | - | - | 
| app_id | 应用ID | id | 否 | - | - | - | - | 
| app_key | 应用标识 | string | 否 | - | - | - | - | 
| app_name | 应用名称 | string | 否 | - | - | - | - | 
| login_time | 登录时间 | time | 否 | - | - | ${time} | - | 
| status | 状态 | string | 否 | - | - | - | - | 
| status_desc | 状态描述 | string | 否 | - | - | - | - | 
| ip | IP地址 | string | 否 | - | - | - | - | 

### 17、系统通知 (sys_notice_log)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| log_id | 日志主键 | uuid | 否 | - | - | - | - | 
| message_title | 标题 | string | 否 | - | - | - | - | 
| message_type | 类型 | string | 否 | - | - | - | - | 
| sender | 发送者 | string | 否 | - | - | - | - | 
| send_time | 发送时间 | time | 否 | - | - | - | - | 
| message_body | 消息内容 | text | 否 | - | - | - | - | 
| remind_content | 提醒内容 | text | 否 | - | - | - | - | 
| attachments | 附件 | string | 否 | - | - | - | - | 
| action_id | 视图动作 | id | 否 | - | - | - | - | 
| data_id | 数据ID | id | 否 | - | - | - | - | 
| template_id | 模板 | id | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 
| receiver | 接收者 | sys_notice_receiver | 否 | - | - | - | - | 

### 18、通知接收者 (sys_notice_receiver)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| receiver_id | 接收者ID | uuid | 否 | - | - | - | - | 
| log_id | 日志ID | id | 否 | - | - | - | - | 
| receiver | 接收者 | id | 否 | - | - | - | - | 
| receive_type | 接受者类型 | string | 否 | - | - | - | - | 
| email | Email | email | 否 | - | - | - | - | 
| send_status | 邮件状态 | string | 否 | - | - | - | - | 
| mobile | 手机 | string | 否 | - | - | - | - | 
| remind_status | 手机状态 | string | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 

### 19、通知规则 (sys_notice_rule)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| rule_id | 规则ID | uuid | 否 | - | - | - | - | 
| template_id | 发送模板 | id | 否 | - | - | - | - | 
| org_id | 组织 | wordbook | 否 | - | - | - | - | 
| role_id | 角色 | wordbook | 否 | - | - | - | - | 
| contacts_role_id | 联系人角色 | wordbook | 否 | - | - | - | - | 
| contacts_id | 联系人 | wordbook | 否 | - | - | - | - | 
| receiver_condition | 接收者规则 | text | 否 | - | - | - | - | 
| data_condition | 数据规则 | text | 否 | - | - | - | - | 
| type | 类型 | string | 否 | - | - | - | - | 
| remind_type | 提醒类型 | string | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 
| creator | 创建者 | id | 否 | - | - | - | - | 

### 20、通知模板 (sys_notice_template)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| template_id | 模板ID | uuid | 否 | - | - | - | - | 
| template_name | 模板名称 | string | 是 | - | - | - | - | 
| template_desc | 模板描述 | string | 否 | - | - | - | - | 
| template_type | 模板类型 | string | 否 | - | - | - | - | 
| template_title | 模板标题 | string | 否 | - | - | - | - | 
| template_content | 模板内容 | text | 否 | - | - | - | - | 
| remind_type | 提醒类型 | string | 否 | - | - | - | - | 
| remind_template_name | 提醒模板名称 | string | 否 | - | - | - | - | 
| remind_template | 提醒模板内容 | text | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 
| creator | 创建者 | id | 否 | - | - | - | - | 
| rule | 规则 | sys_notice_rule | 否 | - | - | - | - | 
| log | 日志 | sys_notice_log | 否 | - | - | - | - | 

### 21、开放账户 (sys_openid)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| uid | UID | uuid | 否 | - | - | - | - | 
| openid | OpenID | string | 否 | - | - | - | - | 
| openid_account | 开放账户 | string | 否 | - | - | - | - | 
| openid_type | 开放账户类型 | string | 否 | - | - | - | - | 
| secret | 安全码 | string | 否 | - | - | - | - | 
| validity | 有效期 | string | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 

### 22、组织机构 (sys_org)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| org_id | 组织主键 | uuid | 是 | - | - | - | - | 
| org_name | 组织名称 | string | 是 | - | - | - | - | 
| org_code | 组织编码 | alphanumeric | 否 | - | - | - | - | 
| org_alias | 组织别名 | string | 否 | - | - | - | - | 
| org_stitle | 组织简称 | string | 否 | - | - | - | - | 
| parent_org_id | 父组织 | wordbook | 否 | - | - | - | - | 
| org_level | 组织级别 | string | 否 | - | - | - | - | 
| org_desc | 组织描述 | string | 否 | - | - | - | - | 
| sort_num | 组织排序 | integer | 否 | - | - | - | - | 
| status | 数据状态 | string | 否 | - | - | - | - | 
| is_parent_default | 上级默认 | bool | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 
| creator | 创建者 | id | 否 | - | - | - | - | 

### 23、系统角色 (sys_role)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| role_id | 角色主键 | uuid | 否 | - | - | - | - | 
| role_name | 角色名称 | string | 是 | - | - | - | - | 
| role_code | 角色编码 | string | 是 | - | - | - | 1 | 
| app_id | 应用主键 | id | 是 | - | - | - | - | 
| role_desc | 角色描述 | string | 否 | - | - | - | - | 
| sort_num | 序号 | integer | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 
| role_res | 角色资源 | collection | 否 | - | - | - | - | 
| account | 角色用户 | sys_account | 否 | - | - | - | - | 

### 24、角色资源 (sys_role_res)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| relation_id | 关系主键 | uuid | 是 | - | - | - | - | 
| role_id | 角色 | wordbook | 是 | - | - | - | - | 
| res_id | 资源 | wordbook | 是 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 
| parent_res_id | 父资源 | id | 否 | - | - | - | - | 

### 25、视图设置 (sys_view_setting)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| setting_id | 主键 | uuid | 是 | - | - | - | 1 | 
| view_id | 视图id | id | 否 | - | - | ${appKey} | - | 
| setting_info | 设置信息 | text | 否 | - | - | - | - | 
| data_status | 数据状态 | string | 否 | - | - | normal | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 