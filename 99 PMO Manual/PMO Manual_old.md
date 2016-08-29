# Global Introduction / 全局说明

## Main View / 主视图

![](https://attachments.tower.im/tower/438b89d24f8e45b4abd49fd8b6d98062?filename=PMO-1.png)
- **A, Module Function Menu / 模块导航菜单**
点击切换功能模块，同时模块子菜单（ C 区）联动更新显示，深色背景代表当前所在功能模块名称。
- **B, Account Function Menu / 账号菜单**
点击图标分别进行个人信息查看、修改密码、查看系统通知、注销当前登录账号等操作。
- **C, Sub Function Menu / 模块子菜单**
显示模块导航菜单（ A 区）选定模块的子级功能菜单，背景色高亮的条目代表当前所打开的功能视图名称。
- **D, Action Bar / 动作按钮栏**
点击按钮后进行相关的数据处理操作，例如创建、修改、删除等。高亮颜色按钮仅表示该动作为关键或高频功能。
- **E, Setting Bar / 视图设置栏**
点击按钮后进行视图设置、视图显示模式切换等个性化设置操作。
- **F, Filter Bar / 过滤器栏**
输入或选择数据项控件之后，数据列表（G 区）会根据输入或选择的条件过滤筛选显示数据。
- **G, Data List / 数据列表**
数据内容列表，循环显示多行数据内容，点击行内区域切换选定当前行，如果不点击多选控件（见 K 区）只能选定当前行，选定数据后动作按钮栏（ D 区）会根据功能要求显示或隐藏动作按钮，数据选定状态栏（ H 区）数据选定状态随之更新。点击高亮数据项，打开当前数据行的详情视图（见 P,Q,R 区）。
- **H, Selected Status Bar / 数据选定状态栏**
显示当前数据列表的行号、总数据条数，数据列表选定数据时实时更新统计选定数据条数。
- **I, Pagination Bar / 分页栏**
当数据列表条数较多时需要分页显示数据，点击分页栏页码按照顺序过滤筛选显示数据。

## Data Selected List / 数据选定列表

![](https://attachments.tower.im/tower/046db2e3e52848e2b1ad571247e3328d?filename=PMO-3.png)

- **J, Selected Action Bar 选定数据后的动作栏**
数据列表选定数据时，动作按钮栏(见 D 区)实时显示或隐藏与选定状态和条数有关联的动作按钮。
- **K, Multi-select Controls 多选控件**
数据列表选定时，点击多选控件可以同时选定多行数据。
- **L, Selected Rows 选定行**
数据行选定时高亮显示行背景色和前景文字颜色。

## Data Edit Form / 数据编辑表单

![](https://attachments.tower.im/tower/aff698584aee4116abd5d0ca19732f4b?filename=PMO-4.png)

点击创建和更新数据的动作按钮后，会以模式窗口方式弹出数据输入表单。数据输入时会覆盖主视图并冻结其相关操作，数据编辑后按 “ESC” 键会关闭数据输入表单窗口且不会向服务器提交数据。

- ** M, Close Button / 关闭按钮**
点击关闭按钮，会关闭数据输入表单窗口且不会向服务器提交数据。
- ** N, Error Status Input Control / 错误状态输入控件**
输入内容（或留空）数据不符合定义的数据格式时会以告警颜色高亮显示，鼠标悬停在当前控件时会提醒详细错误信息，表单控件告警颜色显示时无法提交数据，重新获得焦点时恢复正常状态。
- ** O, Window Action Bar / 窗口动作栏**
点击 “Cancel” 按钮时效果与关闭按钮( M 区)相同。点击 “Done” 按钮时会自动验证所有表单项目的数据格式是否正确，当存在错误状态的输入控件时无法提交数据并做告警提醒。如果所有表单项目格式校验正确时自动向服务器提交数据，服务器返回成功状态时自动关闭表单输入窗口并自动刷新主视图数据列表。

## Details View / 详情视图

![](https://attachments.tower.im/tower/f32b63e7c89b4b48be79a65dc9685a67?filename=PMO.png)

主视图数据列表（ G 区）中，点击高亮数据项，打开当前行的详情内容视图。

- **P, Back Button / 返回按钮**
点击返回按钮，关闭详情视图并返回主视图。
- **Q, Subview Tabs / 子视图导航选项卡**
点击子视图导航选项卡在详细内容( R 区)区域内切换显示与当前行关联的子视图。
- **R, Details Content / 详细内容**
详细内容显示区域，显示点击行的详细内容。子视图导航选项卡点击时在该区域切换显示子视图和详细内容。

# Project / 项目管理

## Project / 项目基础信息管理

### Project / 基础信息管理

```
需要确保新增的项目所对应的项目群缩写已经存在，如果不存在，请先在 “Abbreviation Management” 中创建项目群数据后再返回本功能创建项目信息。
```

#### Menu Path / 菜单路径

`Project > Project >Project`

#### Role / 角色

- **NI PMO**
- **NI Director**

#### Filter Bar / 过滤器

- **Status** / 根据项目状态过滤筛选;
- **Abbreviation** / 根据项目群简称过滤筛选;
- **Code** / 根据项目编码模糊检索;
- **Team** / 根据团队过滤筛选;
- **Project** / 根据项目名称模糊检索;

#### Action Bar / 动作按钮

- **Create Project** / 创建新项目;
- **Modify** / 修改选定项目数据（选定）;
- **Remove** / 删除选定项目数据（选定，支持多选）;
- **Documentation** / 文档归档上传（选定，状态必须为 “Close”）；
- **Archive** / 项目归档（选定，状态必须为 “Documentation”）；

```
项目归档后项目信息不再允许更新操作，将只能在项目查询功能中只读查询。
```

### Project Budget （Subview）/ 项目预算管理（子视图）

```
创建和管理预算数据必须先添加项目基础信息后通过数据列表点击进入一个项目的详细内容视图，点击子视图导航选显卡进入项目预算管理子视图。创建的项目预算数据会与详细内容视图所属的项目基础信息自动关联。
```
#### Menu Path / 菜单路径

`Project > Project > Project : Budget`

#### Role / 角色

访问角色与项目基础信息管理一致。

#### Action Bar / 动作按钮

- **Create Budget** / 创建预算数据;
- **Modify** / 修改选定预算信息（选定）;
- **Remove** / 删除选定预算数据（选定，支持多选）; 
- **PR** / 更新选定预算 PR 信息并更新状态为 PR 阶段（选定）;
- **PO** / 更新选定预算 PO 信息并更新状态为 PO 阶段（选定）;
- **GR** / 更新选定预算 GR 信息并更新状态为 GR 阶段（选定）;

### Project Gate (Subview) / 项目关键节点管理（子视图）

#### Role / 角色

访问角色与项目基础信息管理一致。

#### Menu Path / 菜单路径

`Project > Project > Project : Gate`

#### Filter Bar / 过滤器

- **Name** / 根据关键节点名称进行模糊检索;

#### Action Bar / 动作按钮

- **Create Gate** / 创建关键节点;
- **Modify** / 修改选定关键节点信息（选定）;
- **Remove** / 删除选定关键节点（选定，支持多选）; 
- **Actual Finish** / 更新实际完成信息（选定）;

**状态提醒说明**
```
绿色状态灯：已经完成；
黄色状态灯：距离超期还有 3 天；
红色状态灯：超过目标日期；
灰色状态灯：距离超期大于 3 天；
无：没有添加 Gate。
```

### Project Document（Subview） / 项目文档管理 （子视图）

#### Role

访问角色与项目基础信息管理一致。

#### Menu Path / 菜单路径

`Project > Project > Project : Document`

#### Action Bar / 动作按钮

- **Upload Document** / 上传文档；
- **Remove** / 删除选定文件（选定，支持多选）；
- **Download** / 下载选定文件（选定）；

### Project Report（Subview）/ 项目报表(子视图)


#### Role / 角色

访问角色与项目基础信息管理一致。

#### Menu Path / 菜单路径

`Project > Project > Project : Report`

#### Report / 报表

- Budget Overview;
- Actual Cost = GR / PO * 100% ;
- Gate Top 5;

### Team Project / 团队项目基础信息管理

```
功能参见 “Project / 项目基础信息管理”，只可以创建和管理当前角色用户所在团队的项目信息。
```
#### Role / 角色

- **NI PMO**
- **RC PMO**
- **OAQM PMO**
- **PIR PMO**
- **BM PMO**

#### Menu Path / 菜单路径

`Project > Project > Team Project`

### PM Project / PM 项目管理

```
功能参见 “Project / 项目基础信息管理”，只可以创建和管理当前角色用户作为项目经理的项目信息。
```
#### Role / 角色

- **NI PMO**
- **RC PMO**
- **OAQM PMO**
- **PIR PMO**
- **BM PMO**
- **NI PM**
- **RC PM**
- **OAQM PM Auditor**

#### Menu Path / 菜单路径

`Project > Project > My Project`

### Budget / 预算概览

```
全部预算信息查询
```
#### Role / 角色

- **NI PMO**
- **NI Director**

#### Menu Path / 菜单路径

`Project > Project > Budget`

#### Filter Bar / 过滤器

- **Year** / 根据年份过滤筛选;
- **Abbreviation** / 根据缩写过滤筛选;
- **Team** / 根据团队过滤筛选;
- **Budget Type** / 根据预算类型过滤筛选;
- **Code** / 根据项目编码模糊检索;

### RC Executive Project / RC 项目执行管理

#### Role / 角色

- **RC PMO**

#### Menu Path / 菜单路径

`Project > Project > RC Executive Project`

#### Filter Bar / 过滤器

- **Year** / 根据年份去过滤筛选;

#### Action Bar / 动作按钮

- **Create**  / 创建执行项目;
- **Modify**  / 修改选定项目数据（选定）;
- **Remove**  / 删除选定项目数据（选定，支持多选）;

#### RC Executive Project ：Document （Subview） / RC 项目文档管理 (子视图)

#### Role

- **RC PMO**

#### Menu Path / 菜单路径

`Project > RC Executive Project ： Document`

#### Filter Bar / 过滤器

- **Name** / 通过名字模糊查找;
- **Dealer** / 根据经销商过滤;

#### Action Bar / 动作按钮
 
- **Download** / 下载选定文档（选定）;

##  RC Management / RC项目管理

```
创建或导入项目排程之前需要确保 RC 相关的项目基础信息已经存在，如果项目基础信息不存在需要在项目基础信息中添加后再返回添加项目排程。
```

###  Import Schedule / 经销商排程导入

#### Role / 角色

- **RC PMO**

#### Menu Path / 菜单路径

`Project > RC Management > Import Schedule`

#### Filter Bar / 过滤器

- **Year** / 根据年份过滤筛选;
- **Project** / 按照项目过滤筛选;
- **Coach** / 根据培训师过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Region** / 根据地区方位过滤筛选；
- **Ownership** / 根据所有权过滤筛选；
- **PM** / 根据项目经理过滤筛选; 

#### Action Bar / 动作按钮

- **Import Schedule** / 导入经销商项目排程;
- **Create Schedule** / 创建经销商项目排程;
- **Download Template** / 下载排程模版;
- **Remove** / 删除选定排程数据（选定，支持多选）; 
- **Close** / 关闭排程;
- **Start Project** / 项目启动通知发送；

### Schedule Sequence  (Subview) / 经销商排程轮次管理 （子视图）

#### Role / 角色

与经销商排程导入一致。

#### Menu Path / 菜单路径

`Project > RC Management > Import Schedule ：Sequence`

#### Filter Bar / 过滤器

- **Year** / 根据年份过滤
- **Project** / 根据 Project 过滤
- **Coache** / 根据培训师过滤
- **Dealer** / 根据经销商过滤
- **Status** / 根据状态过滤（TBD，confirmed，on-going, finished）
- **Sequence** / 根据轮次过滤（S1，S2，S3,S4）

#### Action Bar / 动作按钮

- **Create Sequence** / 创建轮次;
- **Modify** / 修改轮次内容（选定）;
- **Remove** / 删除选定轮次（选定，支持多选）; 

### Schedule Document  （SubView）/ 排程文档管理 （子视图）

#### Role

与经销商排程导入一致。

#### Menu Path / 菜单路径

`Project > RC Management > Import Schedule ：Document`

#### Filter Bar / 过滤器

- **Name** / 根据名称进行模糊检索;

#### Action Bar / 动作按钮

- **Upload Document** / 上传文档;
- **Download** / 下载文档（选定）;
- **Remove** /删除文档（选定,支持多选）;

### My Project Schedule（PM）  / PM 排程管理

```
功能参见 “Import Schedule / 经销商排程导入”，只可以创建和管理当前角色用户作为项目经理（包括供应商项目经理）的排程信息。
``` 
#### Role / 角色

- **RC PMO**
- **RC PM**
- **Vendor PM**

#### Menu Path / 菜单路径

`Project > RC Management > My Project Schedule`


### DM Schedule （DM） / DM 排程管理

```
区域经理可以查看属于自己管理的经销商项目排程信息并安排进店观察的日期。
```

#### Role / 角色

- **ND DM**

#### Menu Path / 菜单路径

`Project > RC Management > DM Schedule`

#### Filter Bar / 过滤器

- **Year** / 根据年份过滤筛选;
- **Project** / 根据项目过滤筛选;
- **Coache** / 根据培训师过滤筛选;
- **Dealer** / 根据经销商过滤筛选;

#### Action Bar / 动作按钮

- **Observe** / 设置进店观察日期（选定）;

### All Project Schedule / 项目轮次排程总览管理

#### Role / 角色

- **RC PMO**

#### Menu Path / 菜单路径

`Project > RC Management > All Project Schedule`

#### Filter Bar / 过滤器

- **Year** / 根据年份过滤筛选;
- **Project** / 根据项目过滤筛选;
- **Coach** / 根据培训师过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Sequence** / 根据轮次过滤筛选;
- **Status** / 根据轮次状态过滤筛选;

#### Action Bar / 动作按钮

- **Create Sequence** / 创建轮次;
- **Modify** / 修改轮次信息（选定）;
- **Remove** / 删除选定轮次（选定，支持多选）; 

```
项目轮次排程总览管理是 PMO 对导入的排程信息的调整和修改，修改排程日期后不会触发改期通知。
```

### All Project Schedule Document (Subview) / 项目轮次总览文档管理 （子视图）

#### Role / 角色

- **RC PMO**

#### Menu Path / 菜单路径

`Project > RC Management > All Project Schedule：Document`

#### Filter Bar / 过滤器

- **Name** / 根据名称进行模糊查询

#### Action Bar / 动作按钮

- **Upload Document** / 上传轮次文档;
- **Download** / 下载选定文档（选定）;
- **Remove** /删除选定文档（选定，支持多选）

#### All Project Schedule Observer (Subview) / 轮次观察者 （子视图）

```
查看当前轮次的观察者排程列表。
```

#### Role / 角色

- **RC PMO**


#### Menu Path / 菜单路径

`Project > RC Management > All Project Schedule：Observer`

### Notice  / 进店通知管理

```
状态为 “Confirm” 的轮次进店通知。
```

#### Role / 角色

- **RC PMO**

#### Menu Path  / 菜单路径

`Project > RC Management > Notice`

#### Filter Bar / 过滤器

- **Project** / 根据项目过滤筛选;
- **Coach** / 根据培训师过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Sequence** / 根据轮次过滤筛选;

#### Action Bar

- **Send** / 发送通知（选定）;

```
选定轮次后点击 “Send” 后弹出通知邮件预览界面，确认收件人和发送内容无误后点击 “Done” 确认发送。
```

### My Notice  / PM 进店通知管理


```
功能参见 “Notice / 进店通知管理”，只可以发送当前角色用户作为项目经理的进店通知。
```

#### Role

- **RC PMO**

#### Menu Path

`Project > RC Management > My Notice`

### Consulting Management / 咨询管理

```
咨询管理是对项目轮次进店过程的管理。
```
#### Role / 角色

- **RC PMO**

#### Menu Path / 菜单路径

`Project > RC Management > Consulting Management `

#### Filter Bar / 过滤器

- **Project** / 根据项目过滤筛选;
- **Coache** / 根据培训师过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Status** / 根据轮次状态过滤筛选;
- **Sequence** / 根据轮次过滤筛选;
 
#### Action Bar / 动作按钮

- **Reschedule** / 轮次改期（选定，触发通知）;
- **Cancel** / 取消轮次（选定，触发通知）;
- **Report** / 上传轮次计划和报告（选定）;
- **Documentation** / 文档归档检查通过（选定）;
- **Feedback Notice** / 调查问卷通知（选定）;
- **Phone Interview** / 电话回访记录（选定）;

```
系统会在轮次排程开始日期凌晨自动更新轮次状态为 “on going”，轮次排程结束日期次日凌晨自动更新轮次状态为 “finished”。轮次状态更新为 “finished” 之后 14个自然日（10个工作日）内未通过文档归档检查的轮次将红色高亮背景显示，点击 “Documentation” 更新状态后恢复正常显示。
```

### Consulting Document (Subview) / 咨询文档管理 （子视图）

#### Role / 角色

- **RC PMO**

#### Menu Path / 菜单路径

`Project > RC Management > Consulting：Document`

#### Filter Bar / 过滤器

- **Name** / 根据名称进行模糊检索;

#### Action Bar / 动作按钮

- **Upload Document** / 上传文档;
- **Download** / 下载文档（选定）;
- **Remove** /删除文档（选定，支持多选）;



### My Consulting Management / PM咨询管理

```
功能参见 “Consulting Management / 咨询管理”，只可以管理操作当前角色用户作为项目经理的轮次排程。
```

#### Role / 角色

- **RC PMO**
- **RC PM**
- **Vendor PM**

#### Menu Path / 菜单路径

`Project > RC Management > My Consulting Management `


###  My Observe / DM 观察管理

```
区域经理查看和管理自己设置的观察排期。
```

**Role / 角色**

  - **ND DM**；

**Menu Path / 菜单路径**

`Project > RC Management > My Observe`

**Filter Bar / 过滤器**

- **Project** / 根据项目过滤筛选;
- **Coache** / 根据培训师过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Status** / 根据状态过滤筛选;
- **Start Time** / 根据项目开始时间筛选;
- **Sequence** / 根据轮次过滤筛选;

**Action Bar / 动作按钮**

- **Observer** / 设置观察日期（选定）;
- **Cancel Observe** / 取消观察（选定）;

### Consulting History / 咨询历史查询

**Role / 角色**

- **ND DM**

**Menu Path**

`Project > RC Management > Consulting History`

**Filter Bar**

- **Year** / 根据年份去过滤筛选;
- **Project** / 根据项目去过滤筛选;
- **Dealer** / 根据经销商去过滤筛选;
- **Region** / 通过区域过滤筛选;

## OAQM Management / 飞行审计管理

### Fly-in Audit Schedule / 飞行审计排程管理 

#### Role / 角色

- **OAQM PMO**;

#### Menu Path / 菜单路径

`Project > OAQM Management > Fly-in Audit Schedule` 

#### Filter Bar / 过滤器

- **Year** / 根据年份过滤筛选;
- **Auditor 1** / 根据审计员 1 过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Region** / 根据区域过滤筛选;

#### Action Bar 

- **Create Schedule** / 创建排程;
- ** Modify** / 修改排程;
- ** Remove** / 删除排程（选定,支持多选）;
- **Import Schedule** / 导入排程
- **Download Template** / 下载排程模版
- **Next Week Notice** / 下周排程通知

### Fly-in Audit Schedule  Documents (Subview) / 飞行审计排程文档管理 （子视图）

#### Role / 角色

- **OAQM PMO**;

#### Menu Path / 菜单路径

`Project > OAQM Management > Fly-in Audit Schedule：Document`

#### Filter Bar / 过滤器

- **Name** / 根据名称进行模糊检索;

#### Action Bar 

- **Upload Document** / 上传审计文档;
- ** Download** / 下载文档（选定）;
- **Remove** /删除文档（选定，支持多选）

### Fly-in Audit / 审计管理

#### Role / 角色

- **OAQM PMO**

#### Menu Path / 菜单路径

`Project > OAQM Management > Fly-in Audit `

#### Filter Bar / 过滤器

- **Auditor1** / 根据审计员 1 过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Region** / 根据区域过滤筛选;

#### Action Bar / 动作按钮

- **Audit Remind** / 两天后审计排程通知（手动）;
- **Follow-up Remind** / Follow-up 到期提醒（手动）;

```
两天后审计排程通知和 Follow-up 到期提醒是由系统自动发送的通知，一般情况下无需进行收到操作。
```

### Fly-in Audit  Documents (Subview) / 飞行审计文档管理 （子视图）

#### Role / 角色

- **OAQM PMO**;

#### Menu Path / 菜单路径

`Project > OAQM Management > Fly-in Audit ：Document`

#### Filter Bar / 过滤器

- **Name** / 根据名称进行模糊检索;

#### Action Bar / 动作按钮

- **Upload Document** / 上传审计文档;
- **Download** / 下载文档（选定）;
- **Remove** /删除文档（选定，支持多选）;

#### Fly-in Audit Check Format（Subview） / 审计标准管理 (子视图)

#### Role / 角色

- **OAQM PMO**

#### Menu Path / 菜单路径

`Project > OAQM Management > Fly-in Audit ：Check Format`

#### Action Bar  / 动作按钮

- **Add Format** / 添加审计规格;
- **Import Checklist** / 导入审计结果列表;
- **Empty Checklist** / 清空审计结果列表；
- **Remove** / 删除审计规格;
- **Follow—up Result Notice** / Follow—up 整改结果通知;

###  My Fly-in Audit / 审计员审计管理

```
功能参见 “Fly-in Audit / 审计管理”，只可以管理操作当前角色用户作为审计员的经销商排程、审计规格及文档。
```

#### Role / 角色

- **OAQM PMO**
- **OAQM Auditor**
- **OAQM PM Auditor**

#### Menu Path / 菜单路径

`Project > OAQM Management > My Fly-in Audit`

### Result Overview / 审计结果管理

#### Role / 角色

- **OAQM PMO**

#### Menu Path / 菜单路径

`Project > OAQM Management > Result Overview`

#### Filter Bar / 过滤器

- **Year** / 根据年份过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Region** / 根据区域过滤筛选;
- **Follow Up** / 根据是否有 Follow-up 过滤筛选;
- **Format** / 根据格式过滤筛选;

### Result Overview Follow Up（Subview） / 后续整改项目（子视图）

#### Role / 角色

- **OAQM PMO**;

#### Menu Path / 菜单路径

`Project > OAQM Management > Result Overview ：Follow Up`

#### Filter Bar / 过滤器

- **Onsite** / 根据现场结果过滤筛选;
- **Type** / 根据类型过滤筛选;
- **Fly-in Result** / 根据飞行审计结果过滤筛选;
- **Region Check** / 根据区域审计结果过滤筛选;
- **Final Result** / 根据最终结果过滤筛选;

#### Action Bar / 动作按钮

- **Yes** / 更新 Follow Up 结果为“Yes” （选定,支持多选）;
- **No** / 更新 Follow Up 结果为“No”  （选定,支持多选）;
- **Waiting** / 更新 Follow Up 结果 （为“Waiting” 选定,支持多选）;
- **Pending** / 更新 Follow Up 结果为“Pending”  （选定,支持多选）;

### Result Overview Checklist (Subview)  / 审计结果（子视图）

#### Role / 角色

- **OAQM PMO**;

#### Menu Path / 菜单路径

`Project > OAQM Management > Result Overview ：Checklist`

#### Filter Bar / 过滤器

- **Onsite** / 根据现场结果过滤筛选;
- **Type** / 根据类型过滤筛选;
- **Fly-in Result** / 根据飞行审计结果过滤筛选;
- **Region Check** /  根据区域审计结果过滤筛选;
- **Final Result** / 根据最终结果过滤筛选;

#### Action Bar / 动作按钮

- **Import Checklist** / 导入审计标准结果列表;
- **Modify** / 修改审计标准结果（选定）;

```
使用审计规格模板导入审计结果数据时必须将 xlsb 文件另存为普通的 Excel 文件格式（xlsx）。
```

### My Result Overview / 审计员审计结果管理

```
功能参见 “Result Overview Audit / 审计结果管理”，只可以管理操作当前角色用户作为审计员的排程结果导入和操作及文档管理。
```

#### Role / 角色

- **OAQM PMO**
- **OAQM Auditor**
- **OAQM PM Auditor**

#### Menu Path / 菜单路径

`Project > OAQM Management > My Result Overview`

## Calendar / 排程日历

```
排程日历将 OAQM Fly-in Audit 和 RC 项目排程按照月份进行日历展示，对于排程冲突在左侧分组栏红色高亮背景提醒，在底部状态栏提醒冲突数量，同时在日历上加深冲突日期颜色。
```

### Dealer Schedule / 经销排程日历

```
经销商排程日历混合显示 OAQM Fly-in Audit 和 RC 项目排程。
```

#### Role / 角色

- **NI PMO**
- **NI Director**
- **OAQM PMO**

#### Menu Path / 菜单路径

`Calendar > Dealer Schedule`

#### Filter Bar / 过滤器

- **Start Time** / 根据开始时间按月份过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Person** / 根据人员过滤筛选;

### RC Dealer Schedule / RC 经销商排程日历

#### Role / 角色

- **NI PMO**
- **NI Director**
- **RC PMO**
- **RC PM**

#### Menu Path / 菜单路径

`Calendar > RC Dealer Schedule`

#### Filter Bar / 过滤器

- **Dealer** / 根据经销商过滤筛选;
- **Start Time** / 根据开始时间按月份过滤筛选;
- **Project** / 根据工程过滤筛选;
- **Coach** / 根据培训师过滤筛选;
- **Status** / 根据状态过滤筛选;
- **Ownership** / 根据经销商集团过滤筛选;
- **Region** / 根据区域过滤筛选;

### Coach Schedule / 培训师排程日历

#### Role / 角色

- **NI PMO**
- **NI Director**
- **RC PMO**
- **RC PM**

#### Menu Path / 菜单路径

`Calendar > Coach Schedule `

#### Filter Bar / 过滤器哦

- **Start Time** / 根据开始时间按月份过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Project** / 根据项目过滤筛选;
- **Coach** / 根据培训师过滤筛选;
- **Status** / 根据状态过滤筛选;

### Auditor Schedule / 审计员排程日历

#### Role / 角色

- **NI PMO**
- **OAQM PMO**
- **NI Director**
- **OAQM Mgr**

#### Menu Path / 菜单路径

`Calendar > Auditor Schedule`

#### Filter Bar / 过滤器

- **Start Time** / 根据开始时间按月份过滤筛选;
- **Dealer** / 根据经销商过滤筛选;
- **Auditor** / 根据审计员过滤筛选;

### My Calendar / 个人日历

```
显示当前角色用户为项目经理、审计员的相关排程。
```

#### Role / 角色

- **OAQM PMO**
- **OAQM Auditor**
- **RC PMO**
- **RC PM**

#### Menu Path / 菜单路径

`Calendar > My Calendar`

#### Filter Bar / 过滤器

- **Start Time** / 根据开始时间按月份过滤筛选;
- **Dealer** / 根据经销商过滤筛选;

# Report / 报表

## Project / 项目总览报表

- Project Number / 通过各个阶段或状态的项目数量统计;
- Project Gate Status / 根据项目 Gate 状态统计项目数量;
- Deliver Rate / 通过 PO 的项目数量除以通过 PR 的项目总数;
- Budget / Saving 、Cost 与 OP 的对比进度;
- Team Budget Overview
- Split

## RC Project / RC 项目总览报表

```
报表内容及统计方法参见 “Project / 项目总览报表”，只统计 RC 部门数据。
```

## OAQM Project / OAQM 项目总览报表

```
报表内容及统计方法参见 “Project / 项目总览报表”，只统计 OAQM 部门数据。
```

## BM Project / BM 项目总览报表

```
报表内容及统计方法参见 “Project / 项目总览报表”，只统计 BM 部门数据。
```

## PIR Project / PIR 项目总览报表

```
报表内容及统计方法参见 “Project / 项目总览报表”，只统计 PIR 部门数据。
```

## RC Project Progress / RC 项目进度报表

- RC Project Dealer Number / RC 分项目经销商数量统计;
- YTD Sequence Achievement Rate / 年度累计轮次完成情况;
- Project Dealer Number By Region / 项目分区域经销商数量统计;
- Observer Number By Region / 分区域观察者数量统计;
- Project Number By Coach / 分培训师项目数量统计;

## Fly-in Audit / 飞行审计报表

- Audit Report / 审计结果报表;
- Difference Rank / 现场审计与区域审计结果不同标准项数量排名
- Score Rank / 经销商审计分数排名;
- Pass Rate Rank / 审计标准通过率排名;

# Document / 文档管理

```
RC 项目咨询文档总览管理，可以按照不同项目、经销商分类查找项目文档。
```

#### Role / 角色

- **NI PMO**
- **NI Director**
- **RC PMO**
- **RC PM**

#### Menu Path / 菜单路径

`Document`

#### Filter Path / 过滤器

- **Name** / 根据文档名字模糊检索;
- **Dealer** / 根据经销商过滤筛选;
- **Project** / 根据项目过滤筛选;
- **Keyword** / 根据关键字模糊检索;

#### Action Bar / 动作按钮

- ** Download** / 下载文档（选定）;

# System / 系统管理

## Dealer / 经销商相关信息管理

### Region / 区域管理

#### Role / 角色

- **NI PMO**;
- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Dealer > Region`

#### Action Bar / 动作按钮

- **Create Region** / 创建区域;
- **Modify** / 修改选定区域信息;
- **Remove** / 删除选定区域信息（选定,支持多选）;

### Region Contacts （Subview） / 联系人管理 （子视图）

#### Role / 角色

- **NI PMO**;
- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Dealer > Region ： Contacts`

#### Filter Bar / 过滤器

- **Name** / 通过联系人名称模糊检索;

#### Action Bar / 动作按钮

- **Create Contact** / 创建联系人;
- **Modify** / 修改选定联系人信息（选定）;
- **Remove** / 删除选定联系人信息（选定，支持多选）;

### District / 行政区域管理

#### Role / 角色

- **NI PMO**;
- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Dealer > District`
 
#### Action Bar / 动作按钮

- **Create District** / 创建行政区域;
- **Modify** / 修改选定行政区域信息（选定）;
- **Remove** / 删除选定行政区域信息（选定,支持多选）;

### Dealer / 经销商管理

#### Role / 角色

- **NI PMO**;
- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Dealer > Dealer`

#### Filter Path

- **Name** / 根据经销商名称过滤筛选;
- **Code** / 根据编码过滤筛选;
- **District** / 根据行政区过滤筛选;
- **Region** / 根据区域过滤筛选;
- **OwnShip** / 根据经销商集团过滤筛选;

#### Action Bar

- **Create Dealer** / 创建经销商;
- **Modify** / 修改选定经销商信息（选定）;
- **Remove** / 删除选定经销商信息（选定，支持多选）;

## Fly-in Audit / 飞行审计相关数据管理

### Brand / 品牌管理

#### Role / 角色

- **NI PMO**;
- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Fly-in Audit > Brand`

#### Action Bar / 动作按钮

- **Create Brand** / 创建品牌;
- **Modify** / 修改选定品牌信息（选定）;
- **Remove** / 删除选定品牌数据（选定，支持多选）;

### Audit Format / 审计规格管理

#### Role / 角色

- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Fly-in Audit > Audit Format`

#### Action Bar / 动作按钮

- **Create Format** / 创建审计规格;
- **Modify** / 修改选定审计规格信息（选定，）;
- **Remove** / 删除选定审计规格数据（选定，支持多选）;
- **Import Standarlist** / 导入审计标准信息
- **Empty Standarlist** / 清空审计标准信息

### Audit Format Standards（Subview）/ 审计规格标准管理（子视图） 

#### Role / 角色

- **NI PMO**;
- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Fly-in Audit > Audit Format：Standards`

#### Filter Bar / 过滤器

- **Type** / 根据类型过滤筛选;
- **Standard** / 根据标准过滤筛选;

#### Action Bar

- **Create Standard** / 创建审计标准;
- **Import** / 导入审计标准
- **Modify** / 修改选定审计标准信息（选定）;
- **Remove** / 删除选定审计标准数据（选定，支持多选）;

## Project / 项目相关数据管理

### Abbreviation / 项目群缩写管理


#### Role / 角色

- **NI PMO**

#### Menu Path / 菜单路径

`System > Project > Abbreviation`

#### Filter Bar / 过滤器

- **Project** / 按照项目名称模糊检索；
- **Abbreviation** / 按照项目群缩写模糊检索；

#### Action Bar / 动作按钮

- **Create Abbreviation** / 创建项目群缩写;
- **Modify** / 修改选定项目群缩写信息（选定）;
- **Remove** / 删除选定项目群缩写信息（选定，支持多选）;

### Vendor / 供应商管理

#### Role / 角色

- **NI PMO**;

#### Menu Path / 菜单路径

`System > Project > Vendor`

#### Action Bar / 动作按钮

- **Create Vendor** / 创建供应商信息;
- **Modify** / 修改选定供应商数据（选定）;
- **Remove** / 删除选定供应商数据（选定，支持多选）;

## Profile / 资料管理

### Account / 账号管理

#### Role / 角色

- **NI PMO**；

#### Menu Path / 菜单路径

`System > Profile > Account`

#### Filter Bar / 过滤器

- **Account** / 根据账户名称模糊检索;
- **Title** / 根据账户头衔模糊检索;
- **Name** / 根据联系人名字模糊检索;
- **Alias** / 根据联系人别名模糊检索；

#### Action Bar

- **Create Account** / 创建账号;
- **Modify** / 修改选定账号信息（选定）;
- **Remove** / 删除选定账号数据（选定，支持多选）;
- **Reset Password** / 重置选定账号密码为初始化密码（选定，初始密码:```123456```）;

### Contacts / 联系人管理

#### Role / 角色

- **NI PMO**

#### Menu Path / 菜单路径

`System > Profile > Contacts`

#### Filter Bar / 过滤器

- **Name** / 根据联系人名字模糊检索;
- **Alias** / 根据联系人别名模糊检索;
- **Account** / 根据账号过滤筛选;

#### Action Bar

- **Create Contacts** / 创建联系人;
- **Modify** / 修改选定联系人信息（选定）;
- **Remove** / 删除选定联系人数据（选定，支持多选）;

### Team / 团队管理


#### Role / 角色

- **NI PMO**;

#### Menu Path / 菜单路径

`System > Profile > Team`

#### Action Bar / 动作按钮

- **Create Team** / 创建团队;
- **Modify** / 修改选定团队信息（选定）;
- **Remove** / 删除选定团队信息（选定，支持多选）;

### Role  / 角色管理

#### Role / 角色

- **NI PMO**;

#### Menu Path / 菜单路径

`System > Profile > Role`

#### Filter Bar / 过滤器

- **Name** / 根据角色名字模糊检索;

#### Action Bar

- **Create Role** / 创建角色;
- **Modify** / 修改选定角色信息（选定）;
- **Remove** / 删除选定角色数据（选定，支持多选）;

#### Role Account  (Subview) / 角色账号管理(子视图)

```
角色账号子视图下添加账号即代表为添加的账号分配了该角色的权限，一个账号只能添加到一个角色下，如果要更改用户角色请先在旧的角色的账号子视图中删除该账号再添加到新的角色下。
```

#### Role / 角色

- **NI PMO**;
 
#### Menu Path / 菜单路径;

`System > Profile > Role ： Account`

#### Action Bar

- **Create Account** / 添加角色账号;
- **Remove** / 删除选定角色账号（选定，支持多选）;

### Coach / 培训师管理

#### Role / 角色

- **NI PMO**;
- **RC PMO**;

#### Menu Path / 菜单路径

`System > Profile > Coach`

#### Filter Bar / 过滤器

- **Name** / 按照培训师名字模糊检索;

#### Action Bar

- **Create Coaches** / 创建培训师;
- **Modify** / 修改选定培训师信息（选定）;
- **Remove** / 删除选定培训师信息（选定，支持多选）;

### Contacts Role  / 联系人角色管理

#### Role / 角色

- **NI PMO**;

#### Menu Path / 菜单路径

`System > Profile > Contacts Role`

#### Filter Bar / 过滤器

#### Action Bar / 动作按钮

- **Create Contacts Role** / 创建联系人角色;
- **Modify** / 修改选定联系人角色信息（选定）;
- **Remove** / 删除选定联系人角色数据（选定，支持多选）;

### Notification / 通知管理

#### Role / 角色

- **NI PMO**
- **RC PMO**;
- **OAQM PMO**;

#### Menu Path / 菜单路径

`System > Notification`

####Action Bar

- **Create Noticifiation** / 创建通知模版;
- **Modify** / 修改选定通知模板（选定）;
- **Remove** / 删除选定通知数据（选定，支持多选）;

#### Notification Log Management (Subview) / 通知日志管理（子视图）

#### Role / 角色

与通知管理相同。

#### Menu Path / 菜单路径

`System > Notification：Log`

#### Filter Bar / 过滤器

- **Email Status** / 根据邮件状态过滤筛选;
- **Time** / 根据通知发送时间过滤筛选;

#### Notification Rule Management (Subview) / 通知规则管理（子视图）

#### Role / 角色

与通知管理相同。

#### Menu Path / 菜单路径

`System > Notification：Rule`

#### Action Bar / 动作按钮

- **Create Rule** / 创建通知规则；
- **Modify** / 修改选定通知规则信息（选定）;
- **Remove** / 删除选定通知规则信息（选定，支持多选）;

### Variable Management / 系统变量管理

#### Role / 角色

- **NI PMO**;

#### Menu Path / 菜单路径

`System > Variable `

#### Action Bar / 动作按钮

- **Modify** / 修改选定变量信息（选定）;