### 界面设计

![固废入库](/images/16.png)

涉及类：InboundActivity.java

涉及操作：

  1. 扫描仓库(库位、容器、固废)，调用接口，绑定(显示)当前数据关系
  1. 点击搜索按钮，跳转到蓝牙搜索界面
  1. 点击链接按钮，链接已配对的蓝牙称头设备
  1. 点击获取重量按钮，获取蓝牙称头的重量数据，并将该重量平均到已绑定的固废重量上
  1. 点击移除按钮，移除当前固废绑定关系
  1. 点击固废列表项，显示固废的详细信息
  1. 点击退回按钮，退回当前固废
  1. 输入总重量后，将该重量平均到已绑定的固废重量张
  1. 输入固废重量，并将所有已绑定固废重量总和写入总重量中

涉及方法：

|方法名|描述|
|-|-|
|connSocketTask|建立设备的串行通信连接|
|getBarcode|扫描回调|
|backRequest|固废退回|
|showReasonDialog|打开退回原因弹出层|
|openDiscovery|进入搜索蓝牙设备列表页面|
|getRequest|入库查询|
|submitRequest|入库提交|
|startBluetoothDeviceTask|启动蓝牙|
|PairTask|蓝牙配对|
|receiveTask|获取蓝牙串口数据|
