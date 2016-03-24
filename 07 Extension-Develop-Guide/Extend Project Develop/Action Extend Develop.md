### 视图动作扩展

视图动作模块包括增、删、改等通用的视图动作和扩展视图动作。扩展视图动作需要按照视图动作扩展接口规范进行编码，实现复杂的操作业务。

#### 视图动作接口规范

视图动作接口规范包括**参数传入**和**数据返回**
- 参数传入为：ActionContext，详细说明见《扩展开发手册》；
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