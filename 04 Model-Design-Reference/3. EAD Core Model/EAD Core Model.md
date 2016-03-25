### 3. EAD Core Model

EAD 核心配置相关模型

#### 1、应用 (ead_app)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| app_id | 主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| app_key | 应用ID | alpha | 是 | - | - | - | 是 | 是 | 是 |
| app_name | 应用名称 | string | 是 | - | - | - | - | 是 | 是 |
| app_type | 应用类型 | string | 否 | - | - | - | - | 是 | 否 |
| app_desc | 应用描述 | string | 否 | - | - | - | - | 是 | 是 |
| icon | 图标 | string | 否 | - | - | - | - | 是 | 否 |
| small_icon | 小图标 | string | 否 | - | - | - | - | 是 | 否 |
| path | 路径 | string | 否 | - | - | - | - | 是 | 是 |
| domain | 域 | string | 否 | - | - | - | - | 是 | 否 |
| params | 应用参数 | string | 否 | - | - | - | - | 是 | 否 |
| theme | 应用主题 | string | 否 | - | - | - | - | 是 | 是 |
| style | 应用样式 | string | 否 | - | - | - | - | 是 | 是 |
| logo | Logo | string | 否 | - | - | - | - | 是 | 是 |
| template | 应用模板 | string | 否 | - | - | - | - | 是 | 是 |
| session_type | 会话类型 | string | 否 | - | - | - | - | 是 | 否 |
| app_url | 应用URL | string | 否 | - | - | - | - | 是 | 是 |
| language | 语言 | string | 否 | - | - | - | - | 是 | 是 |
| app_navigation | 导航 | bool | 否 | - | - | - | - | 是 | 否 |
| user_profile | 用户资料 | bool | 否 | - | - | - | - | 是 | 否 | 
| remind | 提醒 | string | 否 | - | - | - | - | 是 | 否 |
| app_alias | 别名 | string | 否 | - | - | - | - | 是 | 是 |
| status | 应用状态 | string | 否 | - | - | - | - | 是 | 是 |
| background | 应用背景 | string | 否 | - | - | - | - | 是 | 是 |
| sort_num | 排序 | integer | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |
| app_role | 应用角色 | sys_role | 否 | - | - | - | - | 否 | 是 |
| app_res | 应用资源 | ead_res | 否 | - | - | - | - | 否 | 是 |

#### 2、数据集 (ead_collection)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| collection_id | 集合主键 | uuid | 是 | - | - | - | - | 是 | 是 |
| collection_name | 名称 | string | 是 | - | - | - | - | 是 | 是 |
| model_id | 模型 | wordbook | 否 | - | - | - | - | 是 | 是 |
| query_schema | 查询定义 | text | 否 | - | - | - | - | 是 | 是 |
| maximum | 最大条数 | integer | 否 | - | - | - | - | 是 | 否 | 
| query_raw | 原生查询 | text | 否 | - | - | - | - | 是 | 是 | 
| attr_map | 属性映射 | text | 否 | - | - | - | - | 是 | 否 | 
| query_type | 查询类型 | string | 是 | - | - | - | - | 是 | 是 | 
| collection_type | 集合类型 | string | 否 | - | - | - | - | 是 | 否 |
| source_id | 数据源 | wordbook | 是 | - | - | - | - | 是 | 是 | 
| collection_desc | 集合描述 | string | 否 | - | - | - | - | 是 | 是 | 
| collection_category | 集合分类 | string | 否 | - | - | - | - | 是 | 是 | 
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 | 
| domain | 域 | wordbook | 否 | - | - | - | - | 否 | 是 | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 | 

#### 3、数据源 (ead_data_source)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| source_id | 数据源主键 | uuid | 是 | - | - | - | 是 | 是 | 是 | 
| source_name | 名称 | string | 是 | - | - | - | 是 | 是 | 是 |
| source_type | 类型 | string | 是 | - | - | - | - | 是 | 是 |
| source_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| driver | 驱动 | string | 是 | - | - | - | - | 是 | 是 |
| ip_address | ip | string | 是 | - | - | - | - | 是 | 是 |
| port | port | string | 是 | - | - | - | - | 是 | 是 |
| url | 链接 | string | 是 | - | - | - | - | 是 | 是 |
| user_name | 用户名 | string | 是 | - | - | - | - | 是 | 是 |
| password | 密码 | string | 否 | - | - | - | - | 是 | 是 |
| maximum | 最大连接 | integer | 是 | - | - | - | - | 是 | 是 |
| minimum | 最小连接 | integer | 是 | - | - | - | - | 是 | 是 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| service_name | 库名 | string | 是 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |
| status | 运行状态 | string | 否 | - | - | - | - | 否 | 是 |
| launch_mode | 启动方式 | string | 否 | - | - | - | - | 是 | 是 |

#### 4、数据类型 (ead_data_type)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| type_id | 类型主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| type_name | 类型名称 | string | 是 | - | - | - | - | 是 | 是 |
| type_alias | 别名 | string | 否 | - | - | - | - | 是 | 是 |
| type_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| meta_type | 元类型 | string | 是 | - | - | - | - | 是 | 是 |
| max_length | 最大长度 | integer | 否 | - | - | - | - | 是 | 是 |
| min_length | 最小长度 | integer | 否 | - | - | - | - | 是 | 是 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| verify_rule | 校验规则 | string | 否 | - | - | - | - | 是 | 是 |
| type_object | 类型对象 | text | 否 | - | - | - | - | 是 | 是 |
| is_sys | 系统类型 | bool | 否 | - | - | - | - | 是 | 是 |
| type_category | 类型分类 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |
| list | 枚举列表 | string | 否 | - | - | - | - | 是 | 是 |
| remind | 提醒 | string | 否 | - | - | - | - | 是 | 是 |

#### 5、模型域 (ead_domain)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| domain_id | 域主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| domain_name | 域名称 | string | 是 | - | - | - | 是 | 是 | 是 |
| domain_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| domain_explain | 说明 | string | 否 | - | - | - | - | 是 | 是 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |

#### 6、驱动注册 (ead_driver)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| driver_id | 驱动主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| driver_name | 驱动名称 | string | 是 | - | - | - | 是 | 是 | 是 |
| driver_type | 驱动类型 | string | 是 | - | - | - | - | 是 | 是 |
| driver_uri | 驱动URI | string | 是 | - | - | - | - | 是 | 是 |
| params | 参数 | string | 否 | - | - | - | - | 是 | 否 |
| driver_classify | 驱动类别 | string | 否 | - | - | - | - | 是 | 否 |
| driver_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| domain_id | 域 | wordbook | 是 | - | - | - | - | 是 | 是 |
 
#### 7、模型 (ead_model)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| model_id | 模型主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| model_name | 模型名称 | string | 是 | - | - | - | 是 | 是 | 是 |
| base | 继承 | wordbook | 否 | - | - | - | - | 是 | 是 |
| model_alias | 别名 | string | 是 | - | - | - | - | 是 | 是 |
| model_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| model_type | 类型 | string | 否 | - | - | - | - | 是 | 是 |
| sort_num | 排序 | integer | 否 | - | - | - | - | 是 | 否 |
| model_category | 模型分类 | string | 否 | - | - | - | - | 是 | 是 |
| domain_id | 模型域 | wordbook | 是 | - | - | - | - | 是 | 是 |
| entity | 实体对象 | alphanumeicunline | 否 | - | - | - | - | 是 | 是 |
| data_source | 数据源 | wordbook | 否 | - | - | - | - | 是 | 是 |
| mode | 模式 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| model_attr | 模型属性 | ead_model_attr | 否 | - | - | - | - | 否 | 是 |


#### 8、模型属性 (ead_model_attr)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| model_attr_id | 模型属性主键 | uuid | 是 | - | - | - | 是| 是 | 是 |
| model_id | 所属模型 | wordbook | 是 | - | - | - | - | 是 | 是 |
| attr_name | 名称 | alphanumeicunline | 是 | - | - | - | - | 是 | 是 |
| attr_alias | 别名 | string | 是 | - | - | - | - | 是 | 是 |
| attr_type | 类型 | string | 是 | - | - | - | - | 是 | 是 |
| attr_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| type_id | 数据类型 | wordbook | 是 | - | - | - | - | 是 | 是 |
| required | 必须 | bool | 否 | - | - | - | - | 是 | 是 |
| max_length | 最大长度 | integer | 否 | - | - | - | - | 是 | 是 |
| min_length | 最小长度 | integer | 否 | - | - | - | - | 是 | 是 |
| sort_num | 排序 | integer | 否 | - | - | - | - | 是 | 是 |
| value | 默认值 | string | 否 | - | - | - | - | 是 | 是 |
| unique | 唯一 | bool | 否 | - | - | - | - | 是 | 是 |
| remind | 提醒 | string | 否 | - | - | - | - | 是 | 是 |
| system | 系统 | string | 是 | - | - | - | - | 是 | 是 |
| key_type | 键类型 | string | 否 | - | - | - | - | 是 | 是 |
| is_param | 是否参数 | bool | 否 | - | - | - | - | 是 | 否 |
| foreign_id | 外键 | string | 否 | - | - | - | - | 是 | 是 |
| control | 表单 | string | 否 | - | - | - | - | 是 | 是 |
| list | 枚举列表 | text | 否 | - | - | - | - | 是 | 是 |
| min | 最小值 | number | 否 | - | - | - | - | 是 | 是 |
| max | 最大值 | number | 否 | - | - | - | - | 是 | 是 |
| data_dict | 数据字典 | wordbook | 否 | - | - | - | - | 是 | 是 |
| virtual | 虚拟属性 | string | 否 | - | - | - | - | 是 | 是 |
| verify_rule | 校验规则 | string | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |

#### 9、平台对象 (ead_object)

> 虚拟模型，无实体存在，用于做抽象字典

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- |
| object_id | 对象主键 | uuid | 否 | - | - | - | - |
| object_value | 对象值 | string | 否 | - | - | - | - | 
| sort_item | 排序项 | string | 否 | - | - | - | - | 

#### 10、资源 (ead_res)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| res_id | 资源主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| res_key | 资源编码 | string | 是 | - | - | - | - | 是 | 是 |
| res_path | 资源路径 | string | 否 | - | - | - | - | 是 | 是 |
| res_name | 资源名称 | string | 是 | - | - | - | - | 是 | 是 |
| parent_res_id | 父资源 | wordbook | 否 | - | - | - | - | 是 | 是 |
| res_level | 资源级别 | integer | 否 | - | - | - | - | 是 | 否 |
| res_type | 资源类型 | string | 是 | - | - | - | - | 是 | 是 |
| icon | 图标 | string | 否 | - | - | - | - | 是 | 是 |
| app_id | 应用主键 | wordbook | 否 | - | - | - | - | 是 | 是 |
| object_id | 资源对象 | wordbook | 否 | - | - | - | - | 是 | 是 |
| url | 链接 | url | 否 | - | - | - | - | 是 | 是 |
| res_desc | 资源描述 | string | 否 | - | - | - | - | 是 | 是 |
| res_category | 资源分类 | string | 否 | - | - | - | - | 是 | 是 |
| session_type | 会话类型 | string | 是 | - | - | - | - | 是 | 是 |
| hide | 隐藏 | bool | 否 | - | - | - | - | 是 | 是 |
| sort_num | 排序 | integer | 否 | - | - | - | - | 是 | 是 |
| action | 动作 | string | 否 | - | - | - | - | 是 | 否 |
| is_remind | 提醒 | bool | 否 | - | - | - | - | 是 | 否 |
| allow_mobile | 允许移动设备 | bool | 否 | - | - | - | - | 是 | 否 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |

#### 11、系统变量 (ead_variable)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| var_id | 变量主键 | uuid | 是 | - | - | - | - | 是 | 是 |
| var_name | 变量名称 | string | 是 | - | - | - | 是 | 是 | 是 |
| var_classify | 变量类别 | string | 否 | - | - | - | - | 是 | 否 |
| var_type | 变量类型 | string | 是 | - | - | - | - | 是 | 是 |
| var_category | 变量分类 | string | 否 | - | - | - | - | 是 | 是 |
| params | 参数 | text | 否 | - | - | - | - | 是 | 否 |
| value | 值 | text | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| var_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| domain_id | 域 | wordbook | 是 | - | - | - | - | 是 | 是 |

#### 12、视图 (ead_view)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| view_id | 视图主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| view_name | 视图名称 | string | 是 | - | - | - | - | 是 | 是 |
| view_category | 视图分类 | string | 否 | - | - | - | - | 是 | 是 |
| view_type | 视图类型 | string | 是 | - | - | - | - | 是 | 是 |
| view_mode | 视图模式 | string | 否 | - | - | - | - | 是 | 是 |
| model_id | 模型主键 | wordbook | 是 | - | - | - | - | 是 | 是 |
| collection_id | 查询主键 | wordbook | 否 | - | - | - | - | 是 | 是 |
| display_mode | 显示模式 | string | 是 | - | - | - | - | 是 | 是 |
| view_param | 视图参数 | object | 否 | - | - | - | - | 是 | 是 |
| collection_param | 查询参数 | object | 否 | - | - | - | - | 是 | 是 |
| view_desc | 视图描述 | string | 否 | - | - | - | - | 是 | 是 |
| template | 视图模板 | text | 否 | - | - | - | - | 是 | 否 |
| cache | 缓存 | text | 否 | - | - | - | - | 是 | 否 |
| driver | 驱动 | string | 否 | - | - | - | - | 是 | 否 |
| params | 前端参数 | object | 否 | - | - | - | - | 是 | 否 |
| action | 事件 | string | 否 | - | - | - | - | 是 | 否 |
| icon | 图标 | string | 否 | - | - | - | - | 是 | 否 |
| setting | 设置 | string | 否 | - | - | - | - | 是 | 否 |
| async | 异步 | bool | 否 | - | - | - | - | 是 | 是 |
| handle | 操作类型 | string | 否 | - | - | - | - | 是 | 是 |
| layout | 布局 | string | 否 | - | - | - | - | 是 | 是 |
| extend | 扩展 | string | 否 | - | - | - | - | 是 | 否 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| domain | 域 | wordbook | 否 | - | - | - | - | 是 | 是 |
| default_competence | 默认权限 | string | 否 | - | - | - | - | 是 | 是 |
| super_admin | 超级管理员 | string | 否 | - | - | - | - | 是 | 是 |
| view_attr | 视图属性 | ead_view_attr | 否 | - | - | - | - | 否 | 是 |
| view_action | 视图动作 | ead_view_action | 否 | - | - | - | - | 否 | 是 |
| view_filter | 视图过滤器 | ead_view_filter | 否 | - | - | - | - | 否 | 是 |

#### 13、视图动作 (ead_view_action)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| action_id | 动作主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| action_name | 名称 | string | 是 | - | - | - | - | 是 | 是 |
| action_type | 类型 | string | 否 | - | - | - | - | 是 | 否 |
| driver | 驱动 | wordbook | 否 | - | - | - | - | 是 | 是 |
| action_param | 动作参数 | object | 否 | - | - | - | - | 是 | 是 |
| action | 前端事件 | string | 否 | - | - | - | - | 是 | 是 |
| view_id | 所属视图 | id | 是 | - | - | - | - | 是 | 是 |
| params | 前端参数 | object | 否 | - | - | - | - | 是 | 否 |
| icon | 图标 | string | 否 | - | - | - | - | 是 | 是 |
| selected | 选择模式 | string | 否 | - | - | - | - | 是 | 是 |
| primary | 主要 | bool | 否 | - | - | - | - | 是 | 是 |
| group | 分组 | string | 否 | - | - | - | - | 是 | 是 |
| action_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| view | 操作视图 | wordbook | 否 | - | - | - | - | 是 | 是 |
| flow_model_id | 工作流模型 | wordbook | 否 | - | - | - | - | 是 | 是 |
| method | HTTP方法 | string | 是 | - | - | - | - | 是 | 是 |
| display | 显示模式 | string | 否 | - | - | - | - | 是 | 是 |
| controls | 表单控件 | string | 否 | - | - | - | - | 是 | 否 |
| allow_mobile | 允许手机 | bool | 否 | - | - | - | - | 是 | 否 |
| rule | 规则 | string | 否 | - | - | - | - | 是 | 否 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| action_key | 动作编码 | string | 否 | - | - | - | - | 是 | 是 |
| list | 属性列表 | string | 否 | - | - | - | - | 是 | 是 |
| record_activity | 记录动态 | string | 否 | - | - | - | - | 是 | 是 |

#### 14、视图属性 (ead_view_attr)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| view_attr_id | 视图属性主键 | uuid | 是 | - | - | - | 是 | ---------- | ------- |
| view_attr_name | 名称 | string | 是 | - | - | - | - | 是 | 是 |
| view_attr_alias | 别名 | string | 否 | - | - | - | - | 是 | 否 |
| view_id | 所属视图 | id | 是 | - | - | - | - | 是 | 是 |
| view_attr_desc | 描述 | string | 否 | - | - | - | - | 是 | 是 |
| hidden_type | 隐藏 | string | 否 | - | - | - | - | 是 | 是 |
| template | 模板 | text | 否 | - | - | - | - | 是 | 是 |
| control | 表单 | string | 否 | - | - | - | - | 是 | 是 |
| params | 参数 | object | 否 | - | - | - | - | 是 | 否 |
| value | 默认值 | string | 否 | - | - | - | - | 是 | 是 |
| model_attr_id | 模型属性 | wordbook | 是 | - | - | - | - | 是 | 是 |
| is_sort | 是否排序 | bool | 否 | - | - | - | - | 是 | 否 |
| group | 分组 | string | 否 | - | - | - | - | 是 | 是 |
| display_mode | 显示模式 | string | 否 | - | - | - | - | 是 | 是 |
| ignore | 编辑忽略 | bool | 否 | - | - | - | - | 是 | 是 |
| events | 事件列表 | string | 否 | - | - | - | - | 是 | 否 |
| sub_view_id | 子视图 | wordbook | 否 | - | - | - | - | 是 | 是 |
| access | 权限 | string | 是 | - | - | - | - | 是 | 是 |
| system | 系统 | string | 否 | - | - | - | - | 是 | 是 |
| format | Format | text | 否 | - | - | - | - | 是 | 是 |
| display | Display | text | 否 | - | - | - | - | 是 | 是 |
| column | Column | integer | 否 | - | - | - | - | 是 | 是 |
| dict_mode | 字典模式 | string | 否 | - | - | - | - | 是 | 是 |
| list | 枚举列表 | string | 否 | - | - | - | - | 是 | 是 |
| data_dict | 数据字典 | wordbook | 否 | - | - | - | - | 是 | 是 |
| sort_num | 序号 | integer | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | - | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | - | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | - | - | 是 | 是 |

#### 15、视图过滤器 (ead_view_filter)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 是否物理存储 | 是否启用 |
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | ---------- | ------- |
| filter_id | 过滤器主键 | uuid | 是 | - | - | - | 是 | 是 | 是 |
| filter_type | 类型 | string | 是 | - | - | - | - | 是 | 是 |
| filter_criteria | 条件 | string | 是 | - | - | - | - | 是 | 是 |
| params | 参数 | object | 否 | - | - | - | - | 是 | 否 |
| value | 默认值 | string | 否 | - | - | - | - | 是 | 是 |
| view_attr_id | 视图属性 | wordbook | 是 | - | - | - | - | 是 | 是 |
| required | 必须 | bool | 否 | - | - | - | - | 是 | 是 |
| is_aid | 辅助 | bool | 否 | - | - | - | - | 是 | 否 |
| control | 表单控件 | string | 否 | - | - | - | - | 是 | 是 |
| is_range | 是否区间 | bool | 否 | - | - | - | - | 是 | 是 |
| sort_num | 排序 | integer | 否 | - | - | - | - | 是 | 是 |
| filter_name | 名称 | string | 否 | - | - | - | - | 是 | 是 |
| is_hidden | 隐藏 | bool | 否 | - | - | - | - | 是 | 是 |
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 是 | 是 |
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 是 | 是 |
| view_id | 所属视图 | wordbook | 否 | - | - | - | - | 否 | 是 |
| control_params | 表单参数 | text | 否 | - | - | - | - | 是 | 否 |

