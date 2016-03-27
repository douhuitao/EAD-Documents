### 查询扩展

查询模块包括通用查询和扩展查询。扩展查询需要按照查询扩展接口规范进行编码，实现复杂业务场景。

#### 参数说明

查询扩展接口传入参数为`QueryContext`，详细信息如下：
- View view：当前请求的视图；
- EadView eadView：配置库中视图Bean；
- EadCollection eadCollection：配置库中数据集Bean；
- EadDataSource dataSource：当前数据集对应的数据源；
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
- List<String> findAttrs：查询数据标题列；
- List<EadViewFilterDetail> filters：查询过滤条件列表；
- String query：查询语句；
- Pagination pagination：分页；
- String dataId：详细视图数据ID
- String nodeId：网盘视图父ID
- Long count：数据集长度；
- List<Map<String,Object>> dataList：数据列表；
- Map<String,Object> model：单条数据；
- Map<String,Object> node：数据节点；
- List<Map<String,Object>> parents：自递归数据表父级节点集合；
- boolean exists：数据是否存在；

#### 查询接口规范

查询接口规范包括**参数传入**和**数据返回**
- 参数传入为：QueryContext；
- 数据返回为：`List<Map<String, Object>>`。

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
