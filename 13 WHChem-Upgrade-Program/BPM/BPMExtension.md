## BPM 扩展

### 业务数据主键存储

EAD 平台依赖于全局唯一数据主键进行通用数据模型的管理操作，从 BPM 待办列表重定向到 EAD 详情视图过程中需要传递业务数据主键参数以实现与 EAD 通用管理视图的交互。所以 BPM 对 EAD 平台发起工作流的业务数据主键进行存储支持。

## 重定向 URL Hash 参数支持

EAD 平台路由由前端通过 Hash 进行解析和管理，需要 BPM 支持在 URL Hash 组装参数。 

示例如下：
```
http://hostname:8080/app#bpm/0153cad6e9d7f89b459453c2f0e60209?param1=value2&param2=value2
```
