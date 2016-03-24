### 查询扩展

查询模块包括通用查询和扩展查询。扩展查询需要按照查询扩展接口规范进行编码，实现复杂业务场景。

#### 查询接口规范

查询接口规范包括**参数传入**和**数据返回**
- 参数传入为：QueryContext，详细说明见《扩展开发手册》；
- 数据返回为：List<Map<String, Object>>。

下面是模型属性扩展查询驱动例子：

```
 //由于模型创建时有模型间的继承关系，所以数据列表包括自己本身的属性列表及继承模型的属性列表
 public List<Map<String, Object>> getAllIncludeBase(QueryContext queryContext)
      throws Exception {
    String modelId = queryContext.getView().getParent().getData().getModel()
        .get("model_id").toString();
    EadModel model = eadModelService.getById(modelId);
    List<Map<String, Object>> attrList = new ArrayList<Map<String, Object>>();
    if (model != null) {
      if (StringKit.isBlank(model.getBase())) {
        List<Map<String, Object>> list = eadModelAttrDao.selectByModelId(model.getModelId(), 
            queryContext.getFindAttrs());
        attrList.addAll(list);
      } else {
        addBaseAttrList(model.getModelId(), attrList, queryContext.getFindAttrs());
      }
    }
    //返回 Map 集合列表
    return attrList;
  }

```
