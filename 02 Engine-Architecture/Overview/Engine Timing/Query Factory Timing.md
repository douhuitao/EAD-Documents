### 查询工厂时序图

查询工厂时序图如下所示：

![PNG](..\..\images\10.png)
![PNG](..\..\images\Query Factory.png)

#### 1. 查询工厂

查询工厂根据查询类型不同，实例化不同的查询；

- Rdb : 关系数据库查询；
- Custom : 自定义查询；
- MongoDB : MongoDB 数据查询；

#### 2. 查询

> 注意：所有返回数据统一存放到Data对象

查询执行数据查询工作，从不同的数据源获取数据；

- getData : 获取列表数据；
- getOneData : 获取一条数据；
- getCountData : 获取数据总条数；
- getExistsData : 获取数据是否存在的Data对象；
- getDetailData : 获取数据详细数据；
- getNodeData : 获取网盘数据节点；

#### 3. 视图

以上查询方法按时序图所示，为视图提供数据；


