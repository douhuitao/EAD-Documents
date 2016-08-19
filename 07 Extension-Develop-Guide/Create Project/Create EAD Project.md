### 平台工程创建

首先建立 EAD 工程级目录，把 EAD 所包含的工程及工程文件都拷贝到该目录，项目包括：gbros-root，gbros-hill，gbros-web。

*checkout完代码后，进入以上三个目录，确认是否有.project、.classpath、.setting这些文件，如果有，先进行删除再进行后续操作。*


#### 1. 创建 gbros-hill 项目

在配置安装好的 Eclipse 中建立 gbros-hill 项目，建立方法如下图：

第一步：新建 gbros-hill 项目

在空白处点击右键，选择 `New > Java Project`；
![PNG](..\images\create-ead-project\1.png)

填写项目名称为：gbros-hill，并把路径选择到 **EAD工程级目录下 gbros-hill ** 目录；
![PNG](..\images\create-ead-project\2.png)

完成项目新建
![PNG](..\images\create-ead-project\3.png)

第二步：把 gbros-hill 项目转换成 Maven 项目

在已建立好的项目上点击右键，选择 `Configure > Convert to Maven Project`;
![PNG](..\images\create-ead-project\4.png)

第三步：确认gbros-hill 项目编码

选中项目右键->Properties->Resource->设置编码为UTF-8

#### 2. 创建 gbros-root 项目

在配置安装好的 Eclipse 中建立 gbros-root 项目，建立方法如下图：

第一步：新建 gbros-root 项目

在空白处点击右键，选择 `New > Java Project`；
![PNG](..\images\create-ead-project\5.png)

填写项目名称为：gbros-root，并把路径选择到 **EAD工程级目录下 gbros-root ** 目录；
![PNG](..\images\create-ead-project\6.png)

完成项目新建
![PNG](..\images\create-ead-project\7.png)

第二步：把 gbros-root 项目转换成 Maven 项目

在已建立好的项目上点击右键，选择 `Configure > Convert to Maven Project`;
![PNG](..\images\create-ead-project\8.png)

#### 3. 创建 gbros-web 项目

在配置安装好的 Eclipse 中建立 gbros-web 项目，建立方法如下图：

第一步：新建 gbros-web 项目

在空白处点击右键，选择 `New > Other`；
![PNG](..\images\create-ead-project\9.png)

选择 `Web > Dynamic Web Project`,点击 **Next**；
![PNG](..\images\create-ead-project\10.png)

填写项目名称为：gbros-web，并把路径选择到 **EAD工程级目录下 gbros-web ** 目录；
![PNG](..\images\create-ead-project\11.png)

设置 **Content Root** 目录，完成项目新建
> 注意，Content Root 目录设置为 webapp
![PNG](..\images\create-ead-project\12.png)
![PNG](..\images\create-ead-project\13.png)

第二步：把 gbros-web 项目转换成 Maven 项目

在已建立好的项目上点击右键，选择 `Configure > Convert to Maven Project`;
![PNG](..\images\create-ead-project\14.png)

第三步：设置 gbros-web 项目的 Build Path；

在 gbros-web 项目上点击右键，选择：`Build Path > Configure Build Path`;
![PNG](..\images\create-ead-project\15.png)

添加源码路径，进入 Build Path 后，选择 `Add Forder`,勾选以下目录；
- src > main > java
- src > main > resource
- src > test > java
![PNG](..\images\create-ead-project\16.png)
![PNG](..\images\create-ead-project\17.png)

删除 **src**目录；
![PNG](..\images\create-ead-project\18.png)

完成 Build Path 设置；
![PNG](..\images\create-ead-project\19.png)

第四步：确认gbros-web 项目编码

选中项目右键->Properties->Resource->设置编码为UTF-8
