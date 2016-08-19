# Mongo DB安装 #
## 前提 ##
1. 通知数据中心，升级SUSE操作系统的SSL lib包（libssl.so.1.0.0），由0.9升级到1.0
2. 配置软连接

    \# cd /lib64

    \# ln -s libssl.so.1.0.0 libssl.so.10

    \# ln -s libcrypto.so.1.0.0 libcrypto.so.10
3. 添加lib库并启动

    \# vi /etc/ld.so.conf

    添加如下内容

    /lib64

    保存退出

    重新生效 

    \#Ldconfig


## 上传并解压安装介质  ##
1. 通过root用户上传mongoDB安装包mongodb-linux-x86_64-rhel62-3.2.7.tgz到服务器目录
 
    /usr/local/src

2. 解压安装包并移动到mongoDB安装目录

    \# cd /usr/local/src

    \# tar -xzvf mongodb-linux-x86_64-rhel62-3.2.7.tgz

    \# mv mongodb-linux-x86_64-rhel62-3.2.7 /usr/local/mongodb
## 配置mongoDB ##
1. 创建mongoDB数据库存放路径

    \# mkdir  -p  /home/data/mongodb/mongodb_data/

2. 创建mongoDB数据库日志文件路径

    \# mkdir  -p  /home/data/mongodb/mongodb_log/

3. 启动mongoDB

    \# /usr/local/mongodb/bin/mongod --port 27017 --fork --dbpath=/home/data/mongodb/mongodb_data/ --logpath=/home/data/mongodb/mongodb_log/mongodb.log –logappend

## 配置EAD mongoDB库 ##
进入mongoDB控制台

    # cd /usr/local/mongodb/bin/
    
    # ./mongo
    
    >use admin
    
    >db.createUser(
      {
    user: "root",
    pwd: "password",
    roles:
    [
      {
    role: "userAdminAnyDatabase",
    db: "admin"
      }
    ]
      }
    )

创建ead用户

    >use admin
    
    >db.auth('root','password')
    
    >use ead
    
    >db.createUser({"user": "admin","pwd": "password","roles": ["readWrite","dbAdmin"]})

    