# JRE&Tomcat安装 #
## 1 创建EAD业务用户 ##
1. 通过root用户登录两台，执行

    /# useradd -d /data/ead -m ead

2. 修改密码

    passwd ead

## 2 上传jre及tomcat安装包 ##
1. 通过ead用户，将jre安装包jre-7u80-linux-x64.tar.gz及tomcat安装包上传ead两台服务器home目录/data/ead

## 3 安装jre ##
1. 通过ead用户，解压jre安装包

    >tar -xzvf apache-tomcat-7.0.69.tar.gz

2、	配置环境变量
    vi .bashrc

输入

    export JAVA_HOME=/data/ead/jre1.7.0_80
    export JRE_HOME=/data/ead/jre1.7.0_80
保存退出

    source .bashrc
## 4	安装tomcat ##
1. 通过ead用户，解压jre安装包

    >tar -xzvf apache-tomcat-7.0.69.tar.gz
2. 配置环境变量

    vi .bashrc

输入

    export PATH=$JAVA_HOME/bin:$PATH
    export CATALINA_HOME=/data/ead/apache-tomcat-7.0.69

保存退出

    source .bashrc