### Maven 私服搭建

Apache Maven，是一个软件（特别是Java软件）项目管理及自动构建工具，由Apache软件基金会所提供。基于项目对象模型（缩写：POM）概念，Maven利用一个中央信息片断能管理一个项目的构建、报告和文档等步骤。

EAD 平台的开发使用 Maven 进行依赖包管理、编译、打包，所以在构建工程时需要从 Maven 仓库中下载所依赖的包。

我们可以从 Maven 中央仓库下载所需要的构件（artifact），但这通常不是一个好的做法，首先，Maven 从远程仓库下载所依赖的 jar 包，速度慢，耗时长，且费流量与带宽；其次，在很多企业环境中，为了企业信息安全，都是内网环境，开发人员无法连接远程连接远程 Maven 中央仓库，这就要求必须在企业内网环境中搭建 Maven 私服。通过在本地架设一个 Maven 仓库服务器，在代理远程仓库的同时维护本地仓库，以节省带宽和时间，并且可以应对企业内网环境无法连接 Maven 中央仓库的问题。

Nexus 是 Maven 仓库管理器，可以满足上面的需要。此外，他还提供了强大的仓库管理功能，构件搜索功能，它基于REST，友好的UI是一个extjs的REST客户端，它占用较少的内存，基于简单文件系统而非数据库。这些优点使其日趋成为最流行的Maven仓库管理器。

### 准备工作

下载 Nexus：http://nexus.sonatype.org/downloads/
在下载时，选择：tar.gz 安装包，本次安装使用 nexus-2.12.1-01-bundle.tar.gz；

### 安装配置 Nexus

Nexus提供了两种安装方式，一种是内嵌Jetty的bundle，只要你有JRE就能直接运行。第二种方式是WAR，你只须简单的将其发布到web容器中即可使用。

当前下载的安装包为第一种安装方式。

第一步：把nexus-2.12.1-01-bundle.tar.gz，解压到linux的相应位置；
![PNG](..\images\maven\7.png)

上图中的 nexus-2.12.1-01和sonatype-work目录就是解压tar包后的两个目录，nexus-2.12.1-01 中是 nexus 的核心文件，sonatype-work，会将下载来的开发包放置在其中。
![PNG](..\images\maven\8.png)

```
$ cd nexus-2.12.1-01/
$ ls
```
第二步：启动 nexus；

```
$ ./nexus start
```
![PNG](..\images\maven\9.png)

第三步：nexus启动成功，访问：http://{ip}:8081/nexus/
![PNG](..\images\maven\10.png)

第四步：登录 nexus，用户名：admin，密码：admin123；
![PNG](..\images\maven\11.png)


### 用户开发环境配置连接 Maven 私服

#### 1、设置用户环境全局 Maven setting 文件；
(可到svn目录直接下载setting文件，进行覆盖：https://svnpd.ap.whchem.com/svn/ECS/EAD/trunk/Tools)

```
<profiles>
	<profile>
      <id>nexus</id>
      <repositories>
        <repository>
            <id>nexus</id>
            <name>private nexus</name>
            <url>http://10.211.55.4:8081/nexus/content/groups/public</url>
            <releases><enabled>true</enabled></releases>
            <snapshots><enabled>false</enabled></snapshots>
        </repository>
        <repository>
            <id>nexus-thirdparty</id>
            <name>private nexus</name>
            <url>http://10.211.55.4:8081/nexus/content/repositories/thirdparty</url>
            <releases><enabled>true</enabled></releases>
            <snapshots><enabled>false</enabled></snapshots>
        </repository>
      </repositories>
      <pluginRepositories>
        <pluginRepository>
            <id>nexus</id>
            <name>private nexus</name>
            <url>http://10.211.55.4:8081/nexus/content/groups/public</url>
            <releases><enabled>true</enabled></releases>
            <snapshots><enabled>false</enabled></snapshots>
        </pluginRepository>
        <pluginRepository>
            <id>thirdparty</id>
            <name>local private nexus</name>
            <url>http://10.211.55.4:8081/nexus/content/repositories/thirdparty</url>
            <releases><enabled>true</enabled></releases>
            <snapshots><enabled>false</enabled></snapshots>
        </pluginRepository>
       </pluginRepositories>
    </profile>
  </profiles>

  <activeProfiles>
    <activeProfile>nexus</activeProfile>
  </activeProfiles>
  ```

如有必要，手动设置本地Maven库的地址：

    <localRepository>M:\maven\repository</localRepository>


在首次搭建好 Nexus 时，需要 Maven 私服连接外网。
私服访问或下载规则如下：
- 用户首次编译工程时，会首先到私服去下载包；
  - 如果包在私服不存在，则 Maven 私服会连接 Maven 中央仓库下载包，并在私服进行缓存;
  - 如果包存在，则直接从 Maven 私服进行包下载；
- 其他用户再次进行下载包请求时，就会从 Maven 私服进行获取了，不会连接 Maven 中央仓库；
- 用户自己开发的包可以传到第三方库中，传入方式下面步骤；

传入第三方包，步骤如下：

第一步：登录 nexus，用户名：admin，密码：admin123；
![PNG](..\images\maven\11.png)

第二步：选择第三方库；
![PNG](..\images\maven\12.png)

第三步：上传包；
![PNG](..\images\maven\13.png)
![PNG](..\images\maven\14.png)

#### 2、设置 Java 工程 pom.xml 文件；

```
<repositories>
    <repository>
        <id>nexus</id>
        <name>private nexus</name>
        <url>http://10.211.55.4:8081/nexus/content/groups/public</url>
        <releases>
            <enabled>true</enabled>
        </releases>
        <snapshots>
            <enabled>false</enabled>
        </snapshots>
    </repository>
    <repository>
        <id>nexus-thirdparty</id>
        <name>private nexus</name>
        <url>http://10.211.55.4:8081/nexus/content/repositories/thirdparty</url>
        <releases>
            <enabled>true</enabled>
        </releases>
        <snapshots>
            <enabled>false</enabled>
        </snapshots>
    </repository>
</repositories>
<pluginRepositories>
    <pluginRepository>
        <id>nexus</id>
        <name>private nexus</name>
        <url>http://10.211.55.4:8081/nexus/content/groups/public</url>
        <releases>
            <enabled>true</enabled>
        </releases>
        <snapshots>
            <enabled>false</enabled>
        </snapshots>
    </pluginRepository>
    <pluginRepository>
        <id>nexus-thirdparty</id>
        <name>private nexus</name>
        <url>http://10.211.55.4:8081/nexus/content/repositories/thirdparty</url>
        <releases>
            <enabled>true</enabled>
        </releases>
        <snapshots>
            <enabled>false</enabled>
        </snapshots>
    </pluginRepository>
</pluginRepositories>
```

> 注意：若在工程编译时，发现包不是从 Maven 私服下载，则需要首先删除本机中 .m2\repository 下缓存的包目录，然后重新进行编译；





