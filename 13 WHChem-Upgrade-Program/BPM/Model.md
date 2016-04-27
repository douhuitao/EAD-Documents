## BPM 模型模板
EAD 配置开发基于 BPM 的业务视图，需要定义 BPM 模型模板，开发者只需基于 BPM 模型模板定义业务模型，即可在该模型实例的视图动作配置中使用 BPM 相关通用动作驱动实现和 BPM 的集成。 

### 模型名称

$workflow_bpm

### 模型属性

属性名称|别名|数据类型|描述
:--|:--|:--|:--
bpm_ts_piid|BPM 流程实例 ID|String| 
bpm_status|BPM 状态|String|
bpm_update_time|BPM 更新时间|Time|




