### 编译打包

打开 **gbros-web** 下 pmo.xml，在 pmo.xml 代码上点击右键，选择 `Run As > Maven Install`;
> 注意：初次编译运行时，需要从远程 Maven 仓库下载 Jar 包，时间比较长，请耐心等待。
![PNG](..\images\create-ead-project\20.png)

运行完成后，在 `gbros-web > target` 下查看打包好的 war 包，名称为：gbros-web-1.0.war
![PNG](..\images\create-ead-project\24.png)

> 注意，若运行完成后未出现 war 包，则在工程上进行刷新后重新查看；
> ![PNG](..\images\create-ead-project\25.png)

若在编译打包时发生错误，请先清理工程环境，然后再尝试；
![PNG](..\images\create-ead-project\21.png)
![PNG](..\images\create-ead-project\22.png)