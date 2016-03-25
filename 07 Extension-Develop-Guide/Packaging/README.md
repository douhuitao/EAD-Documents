### 编译打包

打包时，在工程下，找到 pmo.xml，在 pmo.xml 代码上点击右键，选择 `Run As > Maven Install`;
> 注意：初次编译运行时，需要从 Maven 仓库下载 Jar 包，时间比较长，请耐心等待。
![PNG](..\images\create-ead-project\20.png)

#### 整体打包

打开 **gbros-root** 下 pmo.xml，在 pmo.xml 代码上点击右键，选择 `Run As > Maven Install`;
打包时，会根据 pmo.xml 中设置的工程顺序，以此进行打包；
```
  <modules>
    <module>../gbros-hill</module>
    <module>../gbros-web</module>
  </modules>
```
打包完成后，对于不同的工程，会按设置进行打包；
- Java 工程打为 jar 包；
- Java Web 工程打为 war 包；

打包完成后，在项目下 target 目录下可以看到相应的包；

#### 单工程打包

单工程打包时，需要按依赖顺序以此进行打包；
最后部署时，使用 gbros-web 工程 war 包；

运行完成后，在 `gbros-web > target` 下查看打包好的 war 包，名称为：gbros-web-1.0.war
![PNG](..\images\create-ead-project\24.png)

> 注意，若运行完成后未出现 war 包，则在工程上进行刷新后重新查看；
> ![PNG](..\images\create-ead-project\25.png)

若在编译打包时发生错误，请先清理工程环境，然后再尝试；
![PNG](..\images\create-ead-project\21.png)
![PNG](..\images\create-ead-project\22.png)