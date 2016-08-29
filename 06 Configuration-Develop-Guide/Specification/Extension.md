## 扩展开发规范

### 引擎驱动

> 注意，引擎驱动都是依靠Spring Bean + 反射机制执行的，所以在命名是，Spring Bean 名称不能重复；

驱动开发默认命名都采用驼峰命名法，遵循Google Code Style。

#### 自定义视图驱动

包命名：com.xyt.{appName}.view

类命名：驼峰命名法，规则为**应用简称 + 业务名称 + View**，如固废应用：**HwmsBillsView**;

方法名称：view，如：

```
public View view(View view, EadView eadView, ViewContext viewContext) { }
```

#### 自定义视图动作驱动

包命名：com.xyt.{appName}.action;

类命名：驼峰命名法，规则为**应用简称 + 业务名称 + Action**，如固废应用：**HwmsInStoreAction**;

继承规则：extends AbsAction;

方法名称：动作 + 业务名称，如：

```
public Object createInStore(ActionContext context) { }
```

#### 自定义查询驱动

> 通过接口及接口实现完成；如：HwmsOrgService & HwmsOrgServiceImpl

类命名：驼峰命名法，规则为**应用简称 + 业务名称 + Service**，如固废应用：**HwmsOrgService**;

方法名称：get + 业务名称，如：

```
public List<Map<String,Object>> getDepartmentChildsOrg(QueryContext context) { }
```

#### 自定义变量驱动

##### 驱动自定义变量

类命名：驼峰命名法，规则为**应用简称 + 业务名称**;

方法名称：get + 业务名称，如：

```
public Object getDay(EadVariable variable) { }
```

##### Session自定义变量

类命名：驼峰命名法，规则为**应用简称 + 业务名称**;

方法名称：get + 业务名称，如：

```
public Object getDepartmentId(EadVariable variable, Session session) { }
```

### Rainbow 扩展驱动

#### 字符集格式

UFT-8

#### 自定义动作驱动 （Action）

字母、数字和中横线组成扩展名称，多个单词或短语之间使用中横线分隔，例如：```send-mail``` ，以驱动名称作为扩展 JS 文件的文件名（例如：```send-mail.js```）存储到 Rainbow 工程的 ```/js/action/```目录。

#### 自定义视图驱动 （View）

字母、数字和中横线组成扩展名称，多个单词或短语之间使用中横线分隔，例如：```welcome``` ，以驱动名称作为扩展 JS 文件的文件名（例如：```welcome.js```）存储到 Rainbow 工程的 ```/js/view/```目录。