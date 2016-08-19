### 视图动作扩展

视图动作模块包括增、删、改等通用的视图动作和扩展视图动作。扩展视图动作需要按照视图动作扩展接口规范进行编码，实现复杂的操作业务。

#### 参数说明

视图动作扩展接口传入参数为`ActionContext`，详细信息如下：
- View view：当前动作所在视图；
- Model model：当前视图所对应的模型；
- EadView eadView：配置库中视图Bean；
- EadModel eadModel：配置库模型Bean；
- EadViewAction eadAction：配置库视图动作实体；
- Session session：用户会话信息；
- ViewContext viewContext：视图上下文；
  - String url：当前请求地址；
  - HttpMethod method：http方法；
  - Session session：当前会话信息；
  - Map<String, String[]> params：表单参数；
  - List<Map<String, Object>> rawbody：application/json 参数；
  - List<String> rawIds：application/json 参数（操作数据主键列表）；
  - HttpServletRequest request：http请求；
  - EadRes eadRes：当前请求对应的资源；
  - boolean skipAuth：是否忽略权限认证；
  - Boolean readOnly：当前视图是否只读；
- String id：当前操作数据id（url传递）；
- Map<String, Object> data：当前操作数据；
- EngineConfig engineConfig：引擎配置；
- ModelInitialize modelInitialize：模型初始化器；
- DataInitialize dataInitialize：数据初始化器；
- ConfigService configService：配置数据获取接口；
- MessageBuilder messageBuilder：消息构建器；
- QueryFactory queryFactory：查询工厂；

#### 视图动作接口规范

视图动作接口规范包括**参数传入**和**数据返回**
- 参数传入为：ActionContext;
- 数据返回为：Object，一般有两种形式；
  - Object 可以为新增、修改、删除后的对象，数据类型为 Map；
  - Object 可以为操作后的消息，即把通过 ActionContext 传入的 MessageBuilder 构建 Message 进行返回。

下面是创建模型属性的扩展驱动

```
// 新增扩展
public Object create(ActionContext context) throws Exception {
   /**
     这里通过传入的 ActionContext 实现自己的复杂业务，完成后返回新增的对象
    **/
    Map<String,Object> object = context.getData();
    if (!verifyUnique(object.get("model_id").toString(), object)) {
      throw new HillException("model_attr_repeat");
    }
    //通过 Model 把数据新增到数据库中
    object = context.getModel().createEntity(object);
    String modelAttrId = (String)object.get("model_attr_id");
    EadModelAttrDetail modelAttr = eadModelAttrService.getDetailById(modelAttrId);
    EadModel eadModel = eadModelService.getById(modelAttr.getModelId());
    String mode = StringKit.toString(variableFactory.getValue("model_mode"));
    mode = VariableKit.getValue(mode, eadModel.getMode());
    if (eadModel.isAlterMode(mode)) {
      logger.info("Model is alter mode, create entity attr.");
      eadModelAttrService.createColumn(eadModel, modelAttr);
    }
    //返回新增的对象数据
    return object;
  }

```