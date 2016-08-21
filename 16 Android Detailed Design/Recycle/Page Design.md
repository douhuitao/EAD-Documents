### 界面设计

![内部利用转移单](/images/17.png)

涉及类：RecycleActivity.java

涉及操作：

  1. 显示内部利用转移单
  1. 点击列表项，跳转到内部利用详情页面

涉及方法：

|方法名|描述|
|-|-|
|request|获取出库转移单数据|

***

![扫描固废](/images/18.png)

涉及类：RecycleWasteDialogFragment.java

涉及操作：

  1. 显示被扫描的固废信息
  1. 点击移除将该固废从内部利用转移单中移除

***

![内部利用明细](/images/19.png)

涉及类：RecycleItemsActivity.java

涉及操作：

  1. 显示该转移单下已被内部利用的固废
  1. 扫描固废，显示该固废信息
  1. 点击移除按钮，移除当前已内部利用固废
  1. 点击列表项，显示该固废信息
  1. 点击完成按钮，完成内部利用操作，返回到内部利用转移单页面

涉及方法：

|方法名|描述|
|-|-|
|getBarcode|扫描回调|
|submitRequest|内部利用出库|
|recallRequest|移除已出库的内部利用固废|
|completeRequest|完成转移单|
