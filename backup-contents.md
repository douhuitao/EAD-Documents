#Backup Contents

## MongoDB 副本（主从节点）配置

下面看一下怎么一步步搭建一个mongodb的主从复制节点：[操作参考](http://www.lanceyan.com/tech/mongodb/mongodb_cluster_1.html)

#####1 准备两台机器 192.168.0.1 和 192.168.0.2。 192.168.0.1 当作主节点， 192.168.0.2作为从节点。
#####2 分别下载mongodb安装程序包。在192.168.0.1上建立文件夹 /data/mongodbtest/master，192.168.0.2建立文件夹/data/mongodbtest/slave。
#####3 在192.168.0.1启动mongodb主节点程序。注意后面的这个 “ –master ”参数，标示主节点。
`mongod –dbpath /data/mongodbtest/master –master`
输出日志如下，成功！

	[initandlisten] MongoDB starting : pid=18285 port=27017 dbpath=/data/mongodbtest/master master=1
日志显示主节点参数
	
	[initandlisten] options: { dbpath: “/data/mongodbtest/master”, master: true }
	[initandlisten] waiting for connections on port 27017

#####4 在192.168.0.2启动mongodb从节点程序。关键配置，指定主节点ip地址和端口 –source 192.168.0.1:27017 和 标示从节点 –source 参数。

`mongod –dbpath /data/mongodbtest/slave –slave –source 192.168.0.1:27017`

输出日志如下，成功！

	[initandlisten] MongoDB starting : pid=17888 port=27017 dbpath=/data/mongodbtest/slave slave=1
	
日志显示从节点参数

	[initandlisten] options: { dbpath: “/data/mongodbtest/slave”, slave: true, source: “192.168.0.1:27017″ }
	[initandlisten] waiting for connections on port 27017
日志显示从节点 从主节点同步复制数据
	
	[replslave] repl: from host:192.168.0.1:27017
成功！