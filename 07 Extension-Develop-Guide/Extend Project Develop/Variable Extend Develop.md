### 变量扩展

变量模块的获取有三种途径：
- 直接量；
- 用户会话信息；
- 变量驱动执行后的结果；

变量驱动就是为了实现变量的动态获取而编写的一些方法。

#### 参数说明

查询扩展接口传入参数为`EadVariable`，详细信息如下：
- String varName：变量名称；
- String varType：变量类型，包括**值**、**会话**、**驱动**，此处为驱动变量；
- String varCategory：变量分类，包括**平台**、**用户**两个分类；
- String domainId：主题域；
- String params：变量参数
- String value：变量值，变量为驱动变量时，此处为驱动名称；

#### 变量接口规范

变量驱动接口规范包括**参数传入**和**数据返回**
- 参数传入为：EadVariable；
- 数据返回为：Object，必须是基础数据类型，如：String、Integer、Double、Float等。

下面是获取当前时间的扩展驱动

```
/**
   * Get current time
   */
  public Object getNow(EadVariable variable) throws Exception {
    return DateUtils.getTime();
  }

```