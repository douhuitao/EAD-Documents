## BPM 扩展
BPM统一待办后，用户发起、审批、查看第三方流程时，由BPM平台统一跳转到第三方系统流程页面，同时按不同场景下发bpdUri、ts_piid、ts_taskid等非业务字段。本次改造后，需要支持同时下发业务字段，例如业务流程主数据的ID等。

### 1.  数据库表扩充

#### 1.1 扩充第三方系统流程配置表（TS_TRDPTY_BPD_CFG）

- 新增字段 BUSINESS_FIELDS：配置需要下发哪些字段，多个用逗号分隔,VARCHAR2(256)。
- 新增字段 EXT_DATA：扩展数据,VARCHAR2(256)。
- 工作台表元数据配置新增列。

#### 1.2 新增第三方系统统一业务表（WH_BT_TRDPTY）

第三方系统接入BPM，一部分流程不需要存储业务数据，一部分流程需要存储少部分业务数据（如业务数据主键等）。针对以上业务场景，建立统一的第三方系统业务数据表，而非每个流程单独建立业务表。如果后续流程存在特殊需求、统一业务数据表表无法满足时，再单独建立业务表（并不冲突）。

**WH_BT_TRDPTY表结构如下：**

名称|描述|类型
:--|:--|:--
TS_ID|流程实例唯一标识（Primary key）|VARCHAR2(64)
BTNO|流程实例表单号|VARCHAR2(64)
BUSINESS_DATA|第三方系统业务数据（JSON）|VARCHAR2(2048)
CREATE_TIME|创建时间|DATE
UPDATE_TIME|修改时间|DATE
   
### 2.  PD改造

EBTC新增公共服务IS_ SaveBusinessData

**服务名称：** IS_SaveBusinessData

**职责描述：** 新增、修改第三方系统业务数据

**服务来源：** EBTC

**服务封装：** 集成服务

#### 输入 

参数|类型|说明
:--|:--|:--
tsId|String|流程实例唯一标识
btno|String|流程实例表单号
bussinessData|String（JSON）|第三方系统业务数据
params|Json对象|业务参数

#### 输出

参数|类型|说明
:--|:--|:--
responseCode|String|响应码（200代表成功）
responseMessage|String|响应信息

**关键逻辑：**
0. 入参判断，组装参数；
- 调用集成服务IS_SaveProcessBizData_V3；
- 返回结果；

**非功能性需求：**

**使用场景：** 供各业务流程自实现的发起、审批的特殊服务调用（XXX@GS_TrdPty_StartSP、XXX@GS_TrdPty_SubmitSP）

### 3.  工作台改造

**第三方系统下发URL逻辑修改：**
0. 读取第三方系统流程配置表的BUSINESS_FIELDS字段；
- 如果BUSINESS_FIELDS字段不为空，则根据ts_piid读取WH_BT_TRDPTY表；
- 解析业务数据BUSINESS_DATA，按BUSINESS_FIELDS字段组装下发数据，拼接URL返回；
