## SYS

系统模型

### 1、账户 (sys_account)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| uid | 用户主键 | uuid | 否 | - | - | - | 是 | 是 | 是 |
| account | 账号 | alphanumeric | 是 | - | - | - | 是 | 是 | 是 |
| account_code | 编号 | alphanumeric | 否 | - | - | - | - | 是 | 是 |
| user_name | 用户名称 | string | 否 | - | - | - | - | 是 | 是 |
| password | 密码 | password | 否 | - | - | - | - | 是 | 是 |
| email | 邮箱 | email | 否 | - | - | - | - | 是 | 是 |
| phone | 手机 | string | 否 | - | - | - | - | 是 | 是 |
| salt | 安全加盐 | token | 否 | - | - | - | - | 是 | 是 |
| user_type | 用户类型 | string | 否 | - | - | - | - | 是 | 是 |
| register_time | 注册时间 | time | 否 | - | - | - | - | 是 | 是 |
| last_active_time | 最后活动时间 | time | 否 | - | - | - | - | 是 | 是 |
| last_login_time | 最后登录时间 | time | 否 | - | - | - | - | 是 | 是 |
| account_status | 账户状态 | string | 否 | - | - | - | - | 是 | 是 |
| contacts_title | 用户头衔 | string | 否 | - | - | - | - | 否 | 是 |
| abbreviation | 简称 | string | 否 | - | - | - | - | 否 | 是 |
| contacts_alias | 别名 | string | 否 | - | - | - | - | 否 | 是 |
| org_id | 组织 | wordbook | 否 | - | - | - | - | 是 | 是 |
| address | 地址 | string | 否 | - | - | - | - | 否 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| role | 角色 | sys_role | 否 | - | - | - | - | 否 | 是 |

### 2、联系人账户 (sys_account_contacts)

> 虚拟模型，不存在实体，用于字典展示

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- |
| uid | 用户主键 | uuid | 否 | - | - | - | - |
| account | 账户 | string | 否 | - | - | - | - |
| user_name | 用户名 | string | 否 | - | - | - | - | 
| role_id | Role | id | 否 | - | - | - | - | 
| role_name | Role Name | string | 否 | - | - | - | - | 
| role_code | Role Code | string | 否 | - | - | - | - | 

### 3、用户角色 (sys_account_role)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| relation_id | 关系主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| uid | 用户主键 | wordbook | 是 | - | - | - | - | 是 | 是 |
| role_id | 角色主键 | wordbook | 是 | - | - | - | - | 是 | 是 |
| is_default | 是否默认 | bool | 否 | - | - | - | - | 是 | 是 |
| account | 账号 | string | 否 | - | - | - | - | 否 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |

### 4、系统动态 (sys_activity)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| activity_id | 主键 | uuid | 否 | - | - | - | - | 是 | 是 |
| activity_actor | 操作者 | wordbook | 否 | - | - | - | - | 是 | 是 |
| role_id | 角色 | wordbook | 否 | - | - | - | - | 是 | 是 |
| app_id | 应用 | wordbook | 否 | - | - | - | - | 是 | 是 |
| res_id | 资源 | wordbook | 否 | - | - | - | - | 是 | 是 |
| action_id | 操作 | wordbook | 否 | - | - | - | - | 是 | 是 |
| view_id | 视图 | wordbook | 否 | - | - | - | - | 是 | 是 |
| data_id | 数据 | id | 否 | - | - | - | - | 是 | 是 |
| action_type | 动作类型 | string | 否 | - | - | - | - | 是 | 是 |
| activity_content | 动态内容 | string | 否 | - | - | - | - | 是 | 是 |
| before_data | 操作前数据 | text | 否 | - | - | - | - | 是 | 是 |
| after_data | 操作后数据 | text | 否 | - | - | - | - | 是 | 是 |
| activity_path | 路径 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| activity_actor_account | 操作账户 | string | 否 | - | - | - | - | 是 | 是 |
| activity_actor_name | 操作者名称 | string | 否 | - | - | - | - | 是 | 是 |
| role_name | 角色 | string | 否 | - | - | - | - | 是 | 是 |
| app_name | 应用 | string | 否 | - | - | - | - | 是 | 是 |
| res_name | 资源 | string | 否 | - | - | - | - | 是 | 是 |
| action_name | 操作 | string | 否 | - | - | - | - | 是 | 是 |
| view_name | 视图 | string | 否 | - | - | - | - | 是 | 是 |
| node_id | 节点 | id | 否 | - | - | - | - | 是 | 是 |

### 5、网盘权限 (sys_box_competence)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| competence_id | 权限主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| node_id | 节点主键 | id | 是 | - | - | - | - | 是 | 是 |
| uid | 用户主键 | id | 是 | - | - | - | - | 是 | 是 |
| competence_type | 权限类型 | string | 否 | - | - | - | - | 是 | 是 |
| is_inherit | 是否继承 | bool | 否 | - | - | - | - | 是 | 是 |

### 6、网盘自定义视图 (sys_box_custom_view)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| view_id | 视图主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| view_name | 视图名称 | string | 否 | - | - | - | - | 是 | 是 |
| view_type | 视图类型 | string | 否 | - | - | - | - | 是 | 是 |
| view_title | 视图标题 | string | 否 | - | - | - | - | 是 | 是 |
| view_structure | 视图结构 | string | 否 | - | - | - | - | 是 | 是 |
| html_fragment | HTML片段 | string | 否 | - | - | - | - | 是 | 是 |
| data_status | 数据状态 | string | 否 | - | - | normal | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| invalid_time | 失效时间 | time | 否 | - | - | - | - | 是 | 是 |
| create_user | 创建用户 | string | 否 | - | - | ${uid} | - | 是 | 是 |

### 7、网盘分享 (sys_box_share)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| share_id | 主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| view_id | 视图id | id | 否 | - | - | ${appKey} | - | 是 | 是 |
| users | 分享对象 | string | 否 | - | - | - | - | 是 | 是 |
| node_id | 节点主键 | id | 否 | - | - | - | - | 是 | 是 |
| share_token | 分享令牌 | string | 否 | - | - | - | - | 是 | 是 |
| password | 分享密码 | password | 否 | - | - | - | - | 是 | 是 |
| is_inherit | 是否继承 | bool | 否 | - | - | - | - | 是 | 是 |
| note | 备注 | string | 否 | - | - | - | - | 是 | 是 |
| data_status | 数据状态 | string | 否 | - | - | normal | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| expire_time | 过期时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| node_name | 资源名称 | string | 否 | - | - | - | - | 是 | 是 |

### 8、联系人 (sys_contacts)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| contacts_id | 联系人主键 | uuid | 否 | - | - | - | 是 | 是 | 是 |
| contacts_name | 联系人名称 | string | 是 | - | - | - | - | 是 | 是 |
| contacts_title | 头衔 | string | 否 | - | - | - | - | 是 | 是 |
| contacts_alias | 别名 | string | 否 | - | - | - | - | 是 | 是 |
| abbreviation | 缩写 | string | 否 | - | - | - | - | 是 | 是 |
| phone | 电话组 | string | 否 | - | - | - | - | 是 | 是 |
| email | 邮件组 | email | 否 | - | - | - | - | 是 | 是 |
| address | 地址组 | string | 否 | - | - | - | - | 是 | 是 |
| uid | UID | wordbook | 否 | - | - | - | - | 是 | 是 |
| org_id | 组织 | wordbook | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |

### 9、联系人角色 (sys_contacts_role)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| contacts_role_id | Contacts Role ID | uuid | 是 | - | - | - | - | 是 | 是 |
| role_code | Role Code | string | 是 | - | - | - | - | 是 | 是 |
| role_name | Role Name | string | 是 | - | - | - | - | 是 | 是 |
| note | Note | text | 否 | - | - | - | - | 是 | 是 |
| sort_num | Sort | integer | 否 | - | - | - | - | 是 | 是 |
| status | Status | string | 否 | - | - | - | - | 是 | 是 |
| create_time | Create Time | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | Update Time | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | Creator | id | 否 | - | - | ${uid} | - | 是 | 是 |
| role_type | Role Type | string | 是 | - | - | - | - | 是 | 是 |

### 10、区域 (sys_district)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| district_id | 主键 | uuid | 是 | - | - | - | - | 是 | 是 |
| district_code | 编码 | string | 否 | - | - | - | - | 是 | 是 |
| district_cn_name | 行政区名称 | string | 是 | - | - | - | - | 是 | 是 |
| district_alias | 别名 | string | 否 | - | - | - | - | 是 | 是 |
| parent_district_id | 父级区域 | wordbook | 否 | - | - | - | - | 是 | 是 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| status | 状态 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |

### 11、文档 (sys_document)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| doc_id | 视图主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| doc_name | 视图名称 | string | 是 | - | - | - | - | 是 | 是 |
| doc_type | 视图类型 | string | 否 | - | - | - | - | 是 | 是 |
| doc_title | 视图标题 | string | 否 | - | - | - | - | 是 | 是 |
| keyword | 关键字 | string | 否 | - | - | - | - | 是 | 是 |
| doc_status | 文档状态 | string | 否 | - | - | - | - | 是 | 是 |
| data_status | 数据状态 | string | 否 | - | - | normal | - | 是 | 是 |
| summary | 摘要 | string | 否 | - | - | - | - | 是 | 是 |
| thumbnail | 缩略图 | string | 否 | - | - | - | - | 是 | 是 |
| data_type | 数据类型 | string | 否 | - | - | - | - | 是 | 是 |
| meta_data | 元数据 | text | 否 | - | - | - | - | 是 | 是 |
| raw_data | 原生数据 | text | 否 | - | - | - | - | 是 | 是 |
| web_view | Web 视图 | text | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| updator | 更新者 | string | 否 | - | - | - | - | 是 | 是 |

### 12、收藏 (sys_favorite)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| favorite_id | 主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| view_id | 视图id | id | 否 | - | - | ${appKey} | - | 是 | 是 |
| node_id | 节点主键 | id | 否 | - | - | - | - | 是 | 是 |
| res_id | 资源主键 | id | 否 | - | - | - | - | 是 | 是 |
| favorite_name | 收藏名称 | string | 是 | - | - | - | - | 是 | 是 |
| click_num | 点击数量 | integer | 否 | - | - | - | - | 是 | 是 |
| favorite_type | 收藏类型 | string | 否 | - | - | - | - | 是 | 是 |
| note | 备注 | string | 否 | - | - | - | - | 是 | 是 |
| data_status | 数据状态 | string | 否 | - | - | normal | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| invalid_time | 失效时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 是 | 是 |

### 13、文件记录 (sys_file)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| file_id | 文件主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| origin_id | 元主键 | string | 否 | - | - | - | - | 是 | 是 |
| file_name | 文件名称 | string | 是 | - | - | - | - | 是 | 是 |
| file_type | 文件类型 | string | 否 | - | - | - | - | 是 | 是 |
| file_format | 文件规格 | string | 否 | - | - | - | - | 是 | 是 |
| file_size | 文件长度 | string | 否 | - | - | - | - | 是 | 是 |
| file_ext | 扩展名 | string | 否 | - | - | - | - | 是 | 是 |
| mime_type | MIME类型 | string | 否 | - | - | - | - | 是 | 是 |
| file_info | 文件信息 | text | 否 | - | - | - | - | 是 | 是 |
| storage_engine | 存储引擎 | string | 否 | - | - | - | - | 是 | 是 |
| file_key | 文件 | string | 否 | - | - | - | - | 是 | 是 |
| file_source | 文件地址 | string | 否 | - | - | - | - | 是 | 是 |
| storage_info | 存储信息 | text | 否 | - | - | - | - | 是 | 是 |
| storage_type | 存储类型 | string | 否 | - | - | - | - | 是 | 是 |
| md5_hash | MD5散列 | string | 否 | - | - | - | - | 是 | 是 |
| document_id | 文档主键 | string | 否 | - | - | - | - | 是 | 是 |
| action_id | 视图动作 | string | 否 | - | - | - | - | 是 | 是 |
| file_status | 文件状态 | string | 否 | - | - | normal | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| invalid_time | 失效时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 是 | 是 |

### 14、工作流数据关系 (sys_flow_bridge)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| bridge_id | 主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| case_id | 实例 | wordbook | 是 | - | - | - | - | 是 | 是 |
| data_id | 数据主键 | wordbook | 是 | - | - | - | - | 是 | 是 |
| flow_object | 工作流对象 | text | 是 | - | - | - | - | 是 | 是 |
| uid | 操作者 | id | 是 | - | - | - | - | 是 | 是 |
| flow_create_time | 创建时间 | time | 是 | - | - | - | - | 是 | 是 |
| flow_update_time | 修改时间 | time | 是 | - | - | - | - | 是 | 是 |
| flow_status | 工作流状态 | string | 是 | - | - | - | - | 是 | 是 |

### 15、系统日志 (sys_log)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| log_id | 日志主键 | uuid | 是 | - | - | - | - | 是 | 是 |
| url | 请求URL | string | 是 | - | - | - | - | 是 | 是 |
| session_id | 会话ID | string | 否 | - | - | - | - | 是 | 是 |
| user_id | 当前用户 | wordbook | 否 | - | - | - | - | 是 | 是 |
| brower | 浏览器 | string | 否 | - | - | - | - | 是 | 是 |
| brower_version | 版本 | string | 否 | - | - | - | - | 是 | 是 |
| user_agent | 客户端代理 | text | 否 | - | - | - | - | 是 | 是 |
| ip | IP地址 | string | 否 | - | - | - | - | 是 | 是 |
| os | 操作系统 | string | 否 | - | - | - | - | 是 | 是 |
| screen_size | 屏幕分辨率 | string | 否 | - | - | - | - | 是 | 是 |
| http_method | 请求方法 | string | 否 | - | - | - | - | 是 | 是 |
| content_type | 内容类型 | string | 否 | - | - | - | - | 是 | 是 |
| is_ajax | 是否AJAX请求 | bool | 否 | - | - | - | - | 是 | 是 |
| request_time | 请求时间 | time | 否 | - | - | - | - | 是 | 是 |
| response_time | 响应时间 | time | 否 | - | - | - | - | 是 | 是 |
| device_type | 设备类型 | string | 否 | - | - | - | - | 是 | 是 |
| header | HTTP头 | text | 否 | - | - | - | - | 是 | 是 |
| cookie | Cookie | text | 否 | - | - | - | - | 是 | 是 |
| operation_type | 操作类型 | string | 否 | - | - | - | - | 是 | 是 |
| res_id | 资源 | id | 否 | - | - | - | - | 是 | 是 |
| view_id | 视图 | wordbook | 否 | - | - | - | - | 是 | 是 |
| action_id | 动作 | wordbook | 否 | - | - | - | - | 是 | 是 |
| request_body | 请求内容 | text | 否 | - | - | - | - | 是 | 是 |
| response_body | 响应内容 | text | 否 | - | - | - | - | 是 | 是 |
| status_code | 状态编码 | string | 否 | - | - | - | - | 是 | 是 |
| log_desc | 描述 | text | 否 | - | - | - | - | 是 | 是 |
| app_id | App | wordbook | 否 | - | - | - | - | 是 | 是 |

### 16、登录日志 (sys_login_log)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| log_id | 主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| uid | 用户主键 | id | 否 | - | - | - | - | 是 | 是 |
| account | 登录账户 | string | 否 | - | - | - | - | 是 | 是 |
| user_name | 名称 | string | 否 | - | - | - | - | 是 | 是 |
| org_id | 组织 | id | 否 | - | - | - | - | 是 | 是 |
| org_name | 组织名称 | string | 否 | - | - | - | - | 是 | 是 |
| role_id | 角色ID | id | 否 | - | - | - | - | 是 | 是 |
| role_name | 角色 | string | 否 | - | - | - | - | 是 | 是 |
| app_id | 应用ID | id | 否 | - | - | - | - | 是 | 是 |
| app_key | 应用标识 | string | 否 | - | - | - | - | 是 | 是 |
| app_name | 应用名称 | string | 否 | - | - | - | - | 是 | 是 |
| login_time | 登录时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| status | 状态 | string | 否 | - | - | - | - | 是 | 是 |
| status_desc | 状态描述 | string | 否 | - | - | - | - | 是 | 是 |
| ip | IP地址 | string | 否 | - | - | - | - | 是 | 是 |

### 17、系统通知 (sys_notice_log)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| log_id | 日志主键 | uuid | 否 | - | - | - | 是 | 是 | 是 |
| message_title | 标题 | string | 否 | - | - | - | - | 是 | 是 |
| message_type | 类型 | string | 否 | - | - | - | - | 是 | 是 |
| sender | 发送者 | string | 否 | - | - | - | - | 是 | 是 |
| send_time | 发送时间 | time | 否 | - | - | - | - | 是 | 是 |
| message_body | 消息内容 | text | 否 | - | - | - | - | 是 | 是 |
| remind_content | 提醒内容 | text | 否 | - | - | - | - | 是 | 是 |
| attachments | 附件 | string | 否 | - | - | - | - | 是 | 是 |
| action_id | 视图动作 | id | 否 | - | - | - | - | 是 | 是 |
| data_id | 数据ID | id | 否 | - | - | - | - | 是 | 是 |
| template_id | 模板 | id | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| receiver | 接收者 | sys_notice_receiver | 否 | - | - | - | - | 否 | 是 |

### 18、通知接收者 (sys_notice_receiver)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| receiver_id | 接收者ID | uuid | 否 | - | - | - | 是 | 是 | 是 |
| log_id | 日志ID | id | 否 | - | - | - | - | 是 | 是 |
| receiver | 接收者 | id | 否 | - | - | - | - | 是 | 是 |
| receive_type | 接受者类型 | string | 否 | - | - | - | - | 是 | 是 |
| email | Email | email | 否 | - | - | - | - | 是 | 是 |
| send_status | 邮件状态 | string | 否 | - | - | - | - | 是 | 是 |
| mobile | 手机 | string | 否 | - | - | - | - | 是 | 是 |
| remind_status | 手机状态 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |

### 19、通知规则 (sys_notice_rule)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| rule_id | 规则ID | uuid | 否 | - | - | - | - | 是 | 是 |
| template_id | 发送模板 | id | 否 | - | - | - | - | 是 | 是 |
| org_id | 组织 | wordbook | 否 | - | - | - | - | 是 | 是 |
| role_id | 角色 | wordbook | 否 | - | - | - | - | 是 | 是 |
| contacts_role_id | 联系人角色 | wordbook | 否 | - | - | - | - | 是 | 是 |
| contacts_id | 联系人 | wordbook | 否 | - | - | - | - | 是 | 是 |
| receiver_condition | 接收者规则 | text | 否 | - | - | - | - | 是 | 是 |
| data_condition | 数据规则 | text | 否 | - | - | - | - | 是 | 是 |
| type | 类型 | string | 否 | - | - | - | - | 是 | 是 |
| remind_type | 提醒类型 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |

### 20、通知模板 (sys_notice_template)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| template_id | 模板ID | uuid | 否 | - | - | - | - | 是 | 是 |
| template_name | 模板名称 | string | 是 | - | - | - | - | 是 | 是 |
| template_desc | 模板描述 | string | 否 | - | - | - | - | 是 | 是 |
| template_type | 模板类型 | string | 否 | - | - | - | - | 是 | 是 |
| template_title | 模板标题 | string | 否 | - | - | - | - | 是 | 是 |
| template_content | 模板内容 | text | 否 | - | - | - | - | 是 | 是 |
| remind_type | 提醒类型 | string | 否 | - | - | - | - | 是 | 是 |
| remind_template_name | 提醒模板名称 | string | 否 | - | - | - | - | 是 | 是 |
| remind_template | 提醒模板内容 | text | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |
| rule | 规则 | sys_notice_rule | 否 | - | - | - | - | 否 | 是 |
| log | 日志 | sys_notice_log | 否 | - | - | - | - | 否 | 是 |

### 21、开放账户 (sys_openid)

> 整体还没有启用

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| uid | UID | uuid | 否 | - | - | - | - | 是 | 是 |
| openid | OpenID | string | 否 | - | - | - | - | 是 | 是 |
| openid_account | 开放账户 | string | 否 | - | - | - | - | 是 | 是 |
| openid_type | 开放账户类型 | string | 否 | - | - | - | - | 是 | 是 |
| secret | 安全码 | string | 否 | - | - | - | - | 是 | 是 |
| validity | 有效期 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |

### 22、组织机构 (sys_org)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| org_id | 组织主键 | uuid | 是 | - | - | - | - | 是 | 是 |
| org_name | 组织名称 | string | 是 | - | - | - | - | 是 | 是 |
| org_code | 组织编码 | alphanumeric | 否 | - | - | - | - | 是 | 是 |
| org_alias | 组织别名 | string | 否 | - | - | - | - | 是 | 是 |
| org_stitle | 组织简称 | string | 否 | - | - | - | - | 是 | 是 |
| parent_org_id | 父组织 | wordbook | 否 | - | - | - | - | 是 | 是 |
| org_level | 组织级别 | string | 否 | - | - | - | - | 是 | 是 |
| org_desc | 组织描述 | string | 否 | - | - | - | - | 是 | 是 |
| sort_num | 组织排序 | integer | 否 | - | - | - | - | 是 | 是 |
| status | 数据状态 | string | 否 | - | - | - | - | 是 | 是 |
| is_parent_default | 上级默认 | bool | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |

### 23、系统角色 (sys_role)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| role_id | 角色主键 | uuid | 否 | - | - | - | 是 | 是 | 是 |
| role_name | 角色名称 | string | 是 | - | - | - | 是 | 是 | 是 |
| role_code | 角色编码 | string | 是 | - | - | - | 是 | 是 | 是 |
| app_id | 应用主键 | id | 是 | - | - | - | - | 是 | 是 |
| role_desc | 角色描述 | string | 否 | - | - | - | - | 是 | 是 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| role_res | 角色资源 | sys_role_res | 否 | - | - | - | - | 否 | 是 |
| account | 角色用户 | sys_account | 否 | - | - | - | - | 否 | 是 |

### 24、角色资源 (sys_role_res)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| relation_id | 关系主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| role_id | 角色 | wordbook | 是 | - | - | - | - | 是 | 是 |
| res_id | 资源 | wordbook | 是 | - | - | - | - | 是 | 是 |
| parent_res_id | 父资源 | id | 否 | - | - | - | - | 否 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |

### 25、视图设置 (sys_view_setting)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| setting_id | 主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| view_id | 视图id | id | 否 | - | - | ${appKey} | - | 是 | 是 |
| setting_info | 设置信息 | text | 否 | - | - | - | - | 是 | 是 |
| data_status | 数据状态 | string | 否 | - | - | normal | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建用户 | id | 否 | - | - | ${uid} | - | 是 | 是 |

