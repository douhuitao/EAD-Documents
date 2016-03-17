

## WORKFLOW

工作流模型设计
### 1、工作流实例 (sys_flow_case)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| case_id | 实例主键 | uuid | 是 | - | - | - | 1 | 
| last_step_id | 最近步骤 | wordbook | 是 | - | - | - | - | 
| source_uid | 实例发起者 | wordbook | 否 | - | - | - | - | 
| to_do_users | 用户列表 | text | 否 | - | - | - | - | 
| org_id | 组织 | wordbook | 否 | - | - | - | - | 
| model_id | 工作流模型 | wordbook | 否 | - | - | - | - | 
| case_status | 实例状态 | string | 否 | - | - | - | - | 
| case_status_desc | 状态描述 | string | 否 | - | - | - | - | 
| is_over | 是否结束 | string | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 
| log | 日志 | sys_flow_log | 否 | - | - | - | - | 

### 2、工作流日志 (sys_flow_log)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| case_log_id | 实例记录主键 | uuid | 是 | - | - | - | 1 | 
| case_id | 实例 | wordbook | 是 | - | - | - | 1 | 
| current_user_id | 当前用户 | wordbook | 否 | - | - | - | - | 
| step_id | 步骤 | wordbook | 否 | - | - | - | - | 
| deal_type | 处理标识 | string | 否 | - | - | - | - | 
| deal_desc | 处理说明 | string | 否 | - | - | - | - | 
| deal_time | 处理时间 | time | 否 | - | - | - | - | 
| is_handled_form | 是否操作过表单 | string | 否 | - | - | - | - | 
| deal_note | 处理备注 | text | 否 | - | - | - | - | 
| deal_status | 处理状态 | string | 否 | - | - | - | - | 

### 3、工作流模型 (sys_flow_model)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| model_id | 模型主键 | uuid | 是 | - | - | - | 1 | 
| model_name | 模型名称 | string | 是 | - | - | - | - | 
| model_alias | 模型别名 | string | 否 | - | - | - | - | 
| flow_chart | 模型流程图 | text | 否 | - | - | - | - | 
| model_desc | 说明 | text | 否 | - | - | - | - | 
| sort_num | 序号 | integer | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | ${time} | - | 
| update_time | 更新时间 | time | 否 | - | - | ${time} | - | 
| creator | 创建者 | id | 否 | - | - | ${uid} | - | 
| step | 步骤 | sys_flow_step | 否 | - | - | - | - | 
| case | 实例 | sys_flow_case | 否 | - | - | - | - | 

### 4、工作流步骤 (sys_flow_step)

| 字段名称 | 语义名称 | 数据类型 | 必须 | 最大长度 | 最小长度 | 默认值 | 唯一 | 
| ------- | ------- | ------- | --- | ------- | ------- | ----- | --- | 
| step_id | 步骤主键 | uuid | 是 | - | - | - | 1 | 
| step_name | 步骤名称 | string | 是 | - | - | - | - | 
| model_id | 工作流模型 | wordbook | 是 | - | - | - | - | 
| step_code | 步骤编码 | string | 是 | - | - | - | - | 
| step_type | 步骤类型 | string | 是 | - | - | - | - | 
| before_step_id | 前置步骤 | wordbook | 否 | - | - | - | - | 
| after_step_id | 后置步骤 | wordbook | 否 | - | - | - | - | 
| act_user | 参与用户 | wordbook | 否 | - | - | - | - | 
| act_role | 参与角色 | wordbook | 否 | - | - | - | - | 
| act_org | 参与组织 | wordbook | 否 | - | - | - | - | 
| over_time | 超时时间 | time | 否 | - | - | - | - | 
| over_time_event | 超时事件 | text | 否 | - | - | - | - | 
| status_desc | 状态说明 | text | 否 | - | - | - | - | 
| data_condition | 数据条件 | text | 否 | - | - | - | - | 
| msg_template | 消息模板 | text | 否 | - | - | - | - | 
| back_step | 回退步骤 | wordbook | 否 | - | - | - | - | 
| event_notice | 事件通知 | string | 否 | - | - | - | - | 
| form_param | 表单参数 | text | 否 | - | - | - | - | 
| actor_condition | 操作者条件 | text | 否 | - | - | - | - | 
| allow_skip | 允许跳过 | string | 否 | - | - | - | - | 
| allow_over | 是否完成 | string | 否 | - | - | - | - | 
| allow_back_origin | 是否允许退回起点 | string | 否 | - | - | - | - | 
| is_back_origin | 是否退回起点 | string | 否 | - | - | - | - | 
| sort_num | 步骤序号 | integer | 否 | - | - | - | - | 
| callback_driver | 回调驱动 | text | 否 | - | - | - | - | 
| create_time | 创建时间 | time | 否 | - | - | - | - | 
| update_time | 更新时间 | time | 否 | - | - | - | - | 
| creator | 创建者 | id | 否 | - | - | - | - | 