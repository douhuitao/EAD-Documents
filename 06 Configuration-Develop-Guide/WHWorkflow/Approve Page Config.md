## 审批页面配置

流程审批页面主要包含视图配置、视图动作按钮配置等

### 模型配置

   与发起视图共用模型

### 数据集配置

   与发起视图共用数据集
    
### 视图配置

   视图配置，“前端参数”字段配置为: `{"detail":{"mode":"page"}}   `  ; “驱动”字段配置为： WhbpmView。
   
   视图属性配置，包含字段：bpm_ts_piid（只读+隐藏）、bpm_update_time（只读+隐藏）、bpm_status（只读+隐藏）。

### 动作按钮配置

   流程发起页面必须配置以下动作：
    
#### 1. 提交（驳回到起草环节发起、我的草稿发起）

**名称 ：** 提交 

**编码 ：** start 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmStart 

**动作参数 ：** 
```
{"bizDataFields":"org_code,region_code","bpdUri":"HSEHW@HSE.WastePlan"}
``` 
bizDataFields表示那些业务数据传递给BPM；bpdUri表示发起哪个流程

**前端事件 ：** e.bpm-start 

**图标 ：** glyphicon-check 

**选择模式 ：** 单选 

**显示模式 ：** confirm 

#### 2. 提交（正常审批）

**名称 ：** 提交 

**编码 ：** submit 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmSubmit 

**动作参数 ：** 
```
{"bizDataFields":"org_code,region_code"}
``` 

bizDataFields表示那些业务数据传递给BPM，不配置则默认传递所有业务数据；

**前端事件 ：** e.bpm-submit 

**图标 ：** glyphicon-check 

**选择模式 ：** 单选 

**显示模式 ：** confirm 

#### 3. 完成加签

**名称 ：** 完成加签 

**编码 ：** completeInvolve 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmTurnToDo 

**动作参数 ：** 空

**前端事件 ：** e.bpm-turn-todo 

**图标 ：** glyphicon-check 

**选择模式 ：** 单选 

**显示模式 ：** null 

#### 4. 驳回

**名称 ：** 驳回 

**编码 ：** back 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmBack 

**动作参数 ：** 
```
{"bizDataFields":"org_code,region_code"}
``` 

bizDataFields表示那些业务数据传递给BPM，不配置则默认传递所有业务数据；

**前端事件 ：** e.bpm-back 

**图标 ：** glyphicon-arrow-left 

**选择模式 ：** 单选 

**显示模式 ：** confirm 

#### 5. 转办

**名称 ：** 转办 

**编码 ：** reassign 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmTurnToDo 

**动作参数 ：** 空

**前端事件 ：** e.bpm-turn-todo

**图标 ：** 空

**选择模式 ：** 单选 

**分组 ：** 高级 

**显示模式 ：** null 

#### 6. 加签

**名称 ：** 加签 

**编码 ：** involve 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmTurnToDo 

**动作参数 ：** 空

**前端事件 ：** e.bpm-turn-todo

**图标 ：** 空 

**选择模式 ：** 单选 

**分组 ：** 空（加签、转办、通知一组） 

**显示模式 ：** null

#### 7. 通知

**名称 ：** 通知 

**编码 ：** inform 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmInform

**动作参数 ：** 空

**前端事件 ：** e.bpm-inform

**图标 ：** 空 

**选择模式 ：** 单选 

**分组 ：** 空（加签、转办、通知一组） 

**显示模式 ：** null

#### 8. 审批历史

**名称 ：** 审批历史

**编码 ：** logs 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmLogs 

**动作参数 ：** 空

**前端事件 ：** e.bpm-logs 

**图标 ：** glyphicon-list-alt 

**选择模式 ：** 单选 

**分组 ：** 1

**显示模式 ：** Null 

#### 9. 流程图

**名称 ：** 流程图

**编码 ：** diagram 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmDiagram 

**动作参数 ：** 空

**前端事件 ：** e.bpm-diagram 

**图标 ：** glyphicon-picture 

**选择模式 ：** 单选 

**分组 ：** 1

**显示模式 ：** Null 

#### 10. 注销

**名称 ：** 注销

**编码 ：** cancel 

**HTTP方法 ：** POST 

**驱动 ：** WhbpmCancel 

**动作参数 ：** 空

**前端事件 ：** e.bpm-cancel

**图标 ：** glyphicon-remove 

**选择模式 ：** 单选 

**分组 ：** 1

**显示模式 ：** confirm 
