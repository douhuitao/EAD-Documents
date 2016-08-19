## 发起页面配置

流程发起页面主要包含业务模型配置、视图配置、视图动作按钮配置等

### 模型配置

   进行模型配置，主表模型的“继承”字段必须选中 `$workflow_bpm`
   
   其中bpm_status取值范围：draft|normal|back|finish|cancel

### 数据集配置

   进行数据集配置。
    
### 视图配置

   视图配置，“前端参数”字段配置为: `{"detail":{"mode":"page"}}   `  

   视图属性配置，包含字段：bpm_ts_piid（只读+隐藏）、bpm_update_time（只读+隐藏）、bpm_status（只读+默认draft）

### 流程动作按钮配置

   流程发起页面必须配置以下动作：
    
#### 1. 发起

**名称 ：** 发起 

**编码 ：** start 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmStart 

**动作参数 ：** 
```
{"before":{"and":{"bpm_status":["draft","back"]}},"bizDataFields":"org_code,region_code","bpdUri":"HSEHW@HSE.WastePlan"}
``` 
before配置限制哪些状态的单子可以进行发起操作；bizDataFields表示那些业务数据传递给BPM，不配置则默认传递所有业务数据；bpdUri表示发起哪个流程

**前端事件 ：** e.bpm-start 

**图标 ：** glyphicon-share-alt 

**选择模式 ：** 单选 

**显示模式 ：** confirm 


#### 2. 审批历史

**名称 ：** 审批历史

**编码 ：** logs 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmLogs 

**动作参数 ：** 空

**前端事件 ：** e.bpm-logs 

**图标 ：** glyphicon-list-alt 

**选择模式 ：** 单选 

**显示模式 ：** Null 

#### 3. 流程图

**名称 ：** 流程图

**编码 ：** diagram 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmDiagram 

**动作参数 ：** 空

**前端事件 ：** e.bpm-diagram 

**图标 ：** glyphicon-picture 

**选择模式 ：** 单选 

**显示模式 ：** Null 


### 非流程动作按钮控制（新增、修改、删除等）：

某些场景下，业务单据正在审批中，此时不允许对业务数据进行增删改操作，包括主表和子表数据操作。

主表数据操作限制示例(起草、驳回时才能进行操作)：

    {"before":{"and":{"bpm_status":["draft","back"]}}}

子表数据操作限制示例：

    {"before":{"and":{"..bpm_status":["draft","back"]}}}