### 界面设计

![固废出库转移单](/images/20.png)

涉及类：OutboundActivity.java

涉及操作：

  1. 刷车卡，显示该车卡绑定的出库转移单
  1. 点击列表项，跳转到出库转移详情页面

涉及方法：

|方法名|描述|
|-|-|
|getTagId|刷卡回调|
|request|获取出库转移单数据|

***

![扫描固废](/images/21.png)

涉及类：OutboundDialogFragment.java

涉及操作：

  1. 显示被扫描介质下的所有可出库固废
  1. 点击出库将该组固废出库

***

![固废出库明细](/images/22.png)

涉及类：OutboundItemsActivity.java

涉及操作：

  1. 显示该转移单下已出库的固废
  1. 扫描仓库(库位、容器、固废)，显示该介质下所有可出库固废
  1. 点击移除按钮，移除当前已出库固废
  1. 点击列表项，显示该介质下已出库固废
  1. 刷车卡，完成出库操作，返回出库转移单页面

涉及方法：

|方法名|描述|
|-|-|
|getTagId|刷卡回调|
|getBarcode|扫描回调|
|listRequest|获取出库明细|
|request|固废查询|
|submitRequest|固废出库|
|completeRequest|完成转移单|
