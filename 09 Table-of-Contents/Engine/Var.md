## 系统变量列表

名称|类型|分类|域|值|描述
--|--|--|--|--|--
time|driver|Platform|SYS|now|
month-range|driver|Platform|SYS|monthRangeString|
after-7-days|driver|Platform|SYS|after7Days|
today|driver|Platform|SYS|today|获取当前字符串系统日期
uid|session|Platform|SYS|uid|
orgId|session|Platform|SYS|orgId|
appKey|session|Platform|SYS|appKey|
appId|session|Platform|SYS|appId|应用主键
parentOrgId|session|Platform|SYS|parentOrgId|上级组织机构ID
model-mode|value|Platform|EAD|alter|safe:安全,alter:可更新,drop:删除并创建
action-record-activity|value|Platform|EAD|yes|是否记录系统动态
password|value|Platform|SYS|123456|用户密码重置默认密码
year|value|Custom|SYS|2016|
mail-send-flag|value|Custom|SYS|close|Mail send switch : Value has [close],[open]
sms-send-flag|value|Custom|SYS|close|SMS send switch, Value has [close],[open]
desktop-send-flag|value|Custom|SYS|open|Desktop notice send switch, Value has [close],[open]
holidays|value|Custom|SYS||
mail-test-flag|value|Custom|SYS|open|Mail send system test switch : Value has [close],[open]
mail-test-title|value|Custom|SYS|[系统测试邮件，请忽略]|Mail send system test title.
sms-test-flag|value|Custom|SYS|open|SMS send system test switch : Value has [close],[open]
sms-test-title|value|Custom|SYS|[系统测试，请忽略]|SMS send system test title.
desktop-test-flag|value|Custom|SYS|open|Desktop send system test switch : Value has [close],[open]
desktop-test-title|value|Custom|SYS|[系统测试，请忽略]|Desktop notice send system test title.
login-driver|value|Custom|WANHUA|whLdapAuth|万华LDAP登录驱动
before-filters|value|Custom|WANHUA|ltpaAutoLogin,headTokenAuth,addOrgRegion|中间件注入驱动列表
http-head-key|value|Platform|SYS| | Http Token 认证秘钥
regionId|value|Custom|WANHUA|groupId|用户所在区域主键
regionCode|value|Custom|WANHUA|groupCode|用户所在组织机构区域编码
action-off-apps-activity|value|Platform|EAD| |设置相关应用不记录系统动态（以逗号分隔）
departmentId|value|Custom|WANHUA|getDepartmentId|获取用户所在部门ID
ie-to-chrome-key|value|Custom|WANHUA| | IE到Chrome自动登录Token秘钥
