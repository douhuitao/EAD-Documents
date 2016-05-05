## 集成方式

### LDAP
轻型目录存取协定（英文：Lightweight Directory Access Protocol）是一个开放的，中立的，工业标准的应用协议，通过IP协议提供访问控制和维护分布式信息的目录信息。在本次账户体系集成方案中 EAD 平台将采用 LDAP 协议与 LDAP 服务实现用户登录认证集成。

### SOAP
SOAP（原为 Simple Object Access Protocol 的首字母缩写，即简单对象访问协议）是交换数据的一种协议规范，使用在计算机网络 Web 服务（web service）中，交换带结构信息。SOAP为了简化网页服务器（Web Server）从 XML 数据库中提取数据时，节省去格式化页面时间，以及不同应用程序之间按照 HTTP 通信协议，遵从 XML 格式执行资料互换，使其抽象于语言实现、平台和硬件。在本次账户体系集成方案中 EAD 平台需要参考《统一身份管理-UIM-DLV-标准服务开发说明文档》通过 SOAP（Web Service）的方式接受 LDAP 同步的发生变更的账号和组织机构信息。


### 批量数据导入
LDAP 导出指定范围的用户账号信息和组织机构信息数据的 Excel 文件, 在 EAD 平台上传并解析导入。