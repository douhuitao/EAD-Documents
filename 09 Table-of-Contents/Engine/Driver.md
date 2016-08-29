## 驱动列表

名称|类型|URI|域|描述
--|:------:|--|--|--|--
now|变量|variableFactory/getNow|BASE|获取系统当前时间
year|变量|variableFactory/getYear|BASE|获取当前年份
month|变量|variableFactory/getMonth|BASE|获取：yyyy-MM-01 00:00:00 时间戳
monthRangeString|变量|variableFactory/getMonthRangeString|BASE|"获取：yyyy-MM-01,yyyy-(MM+1)-01"
after7Days|变量|variableFactory/getAfter7Days|BASE|获取距离当前七天后的时间区间
today|变量|variableFactory/getDay|BASE|获取当前字符串型系统日期
modelAttrQuery|查询|eadModelAttrService/getAllIncludeBase|EAD|模型属性查询
modelAttrDictQuery|查询|eadModelAttrService/getIncludeBase|EAD|模型属性字典自定义查询
dataSourceQuery|查询|eadDataSourceService/getDataSourceList|EAD|获取数据源列表，根据Spring加载的数据连接池判断数据源状态
copyMyself|动作|commonAction/copyMyself|BASE|复制数据（只复制自己本身）
copyFamily|动作|commonAction/copyFamily|BASE|复制数据及子视图数据
updateBySetting|动作|commonAction/updateBySetting|BASE|根据数据及动作参数配置条件更新数据
excelImport|动作|commonAction/excelImport|BASE|Excel 导入
download|动作|commonAction/download|BASE|通用下载驱动
excelExport|动作|commonAction/excelExport|BASE|数据导出为Excel
upload|动作|commonAction/upload|BASE|通用上传驱动
excelExportAll|动作|commonAction/excelExportAll|BASE|点击直接导出所有数据
boxUpload|动作|boxAction/upload|BOX|网盘文件上传
boxCatalogNew|动作|boxAction/catalogNew|BOX|网盘新建目录
boxRename|动作|boxAction/reName|BOX|网盘重命名
boxAuth|动作|boxAction/auth|BOX|网盘授权
boxCustomViewSave|动作|boxAction/customViewSave|BOX|网盘自定义视图新增
boxCustomContentSave|动作|boxAction/customContentSave|BOX|网盘自定义内容新增
boxCopy|动作|boxAction/copy|BOX|网盘节点拷贝
boxDownload|动作|boxAction/download|BOX|网盘文件下载
boxMove|动作|boxAction/move|BOX|网盘节点移动
boxTemplate|动作|boxAction/copyTemplate|BOX|新增模板目录
boxSetTemplate|动作|boxAction/setTemplate|BOX|设置模板目录
boxCustomViewUpdate|动作|boxAction/customViewSave|BOX|网盘自定义视图修改
boxCustomContentUpdate|动作|boxAction/customContentSave|BOX|网盘自定义内容修改
boxActivity|动作|boxAction/activity|BOX|网盘动态
modelAttrCreate|动作|modelAttrAction/create|EAD|创建模型属性
modelAttrUpdate|动作|modelAttrAction/update|EAD|模型属性更新
modelAttrRemove|动作|modelAttrAction/delete|EAD|模型属性删除
createEntity|动作|modelAction/createTable|EAD|创建模型实体
resCreate|动作|resAction/create|EAD|创建资源
resUpdate|动作|resAction/update|EAD|更新资源
resRemove|动作|resAction/delete|EAD|删除资源
autoConfig|动作|modelAction/autoConfig|EAD|自动配置视图
viewRemove|动作|viewAction/delete|EAD|视图删除，删除相关联的视图属性、动作、过滤器、资源
copyView|动作|viewAction/copyView|EAD|复制视图、视图属性、动作、视图过滤器
modelRemove|动作|modelAction/delete|EAD|模型删除，删除时校验是否有关联项
initDataSource|动作|dataSourceAction/init|EAD|数据源初始化
destroyDataSource|动作|dataSourceAction/destroy|EAD|数据源销毁
viewActionCreate|动作|viewAction/createViewAction|EAD|创建动作
viewActionRemove|动作|viewAction/deleteViewAction|EAD|删除动作
viewAttrCreate|动作|viewAction/createViewAttr|EAD|创建视图属性
viewAttrUpdate|动作|viewAction/updateViewAttr|EAD|更新视图属性
viewAttrRemove|动作|viewAction/deleteViewAttr|EAD|删除视图属性
viewActionUpdate|动作|viewAction/updateViewAction|EAD|修改动作
variableUpdate|动作|variableAction/update|EAD|更新系统变量时，更新预初始化值
variableRemove|动作|variableAction/delete|EAD|删除变量时，删除预初始化变量
modelmport|动作|modelAction/modelImport|EAD|模型属性导入
viewCreate|动作|viewAction/createView|EAD|视图创建
accountCreate|动作|accountAction/create|SYS|创建账户时，同步写入联系人
resetPassword|动作|accountAction/resetPassword|SYS|密码重置
accountUpdate|动作|accountAction/update|SYS|更新用户账号时，同步更新联系人
roleAuth|动作|roleAction/auth|SYS|角色授权
downloadAttachments|动作|noticeAction/downloadAttachments|SYS|邮件附件下载
messageRemove|动作|messageAction/delete|SYS|Message Log Remove
flowReport|动作|workFlowAction/report|SYS|工作流上报提交
flowCheck|动作|workFlowAction/check|SYS|工作流审批
flowQuery|动作|workFlowAction/query|SYS|工作流查询
headTokenAuth|变量|accountAction/headTokenAuth|EAD|HttpHeadToken认证
uploadToBizData|视图动作|commonAction/uploadToBizData|EAD|上传文件到业务数据
getParentOrgs|查询|sysOrgService/getParentOrgs|SYS|递归获取当前组织机构的上级组织机构
WhbpmStart|视图动作|whbpmAction/start|WANHUA|BPM发起流程
WhbpmSubmit|视图动作|whbpmAction/submit|WANHUA|BPM流程审批
WhbpmCancel|视图动作|whbpmAction/cancel|WANHUA|BPM流程取消
WhbpmBack|视图动作|whbpmAction/back|WANHUA|BPM退回
WhbpmLogs|视图动作|whbpmAction/logs|WANHUA|BPM审批日志
WhbpmTurnToDo|视图动作|whbpmAction/turnToDo|WANHUA|BPM加签转办
WhbpmDiagram|视图动作|whbpmAction/diagram|WANHUA|BPM流程图
WhbpmView|视图|whbpmView/view|WANHUA|BPM视图自定义驱动
WhbpmInform|视图动作|whbpmAction/inform|WANHUA|BPM消息通知
importUserFromLdap|视图动作|ldapAction/importUserFromLdap|WANHUA|从Ldap导入用户
importOrgFromLdap|视图动作|ldapAction/importOrgFromLdap|WANHUA|从Ldap导入组织
importOrgFromExcel|视图动作|ldapAction/importOrg|WANHUA|通过Excel导入组织机构
importUserFromExcel|视图动作|ldapAction/importUser|WANHUA|通过Excel导入用户
whLdapAuth|视图动作|ldapAction/isAuthed|WANHUA|Ldap认证驱动
ltpaAutoAuth|视图动作|ldapAction/ltpaLogin|WANHUA|LTPA自动登录
addOrgRegion|视图动作|ldapAction/addOrgRegion|WANHUA|增加组织机构区域关系







