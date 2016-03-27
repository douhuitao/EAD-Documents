### MongoDB集群搭建

MongoDB在处理非结构化数据时有以下优势：

**大数据量**，可以通过廉价服务器存储大量的数据，轻松摆脱传统mysql单表存储量级限制。

**高扩展性**，MongoDB去掉了关系数据库的关系型特性，很容易横向扩展，摆脱了以往老是纵向扩展的诟病。

**高性能**，MongoDB通过简单的key-value方式获取数据，非常快速。还有MongoDB的Cache是记录级的，是一种细粒度的Cache，所以MongoDB在这个层面上来说就要性能高很多。

**灵活的数据模型**，MongoDB无需事先为要存储的数据建立字段，随时可以存储自定义的数据格式。而在关系数据库里，增删字段是一件非常麻烦的事情。如果是非常大数据量的表，增加字段简直就是一个噩梦。

**高可用**，MongoDB在不太影响性能的情况，就可以方便的实现高可用的架构。MongoDB可以通过mongos、mongo分片就可以快速配置出高可用配置。

MongoDB也可以通过集群的方式实现高可用，MongoDB的集群配置包括以下组件，如图所示：
[资料来源：mongodb.org](https://docs.mongodb.org/manual/core/sharded-cluster-architectures-production/#production-cluster-architecture)

![MongoDB集群配置](../images/mongodb/MongoDB-sharded-cluster-production-architecture.png)

**配置服务器Config Servers：** 在最新的MongoDB3.2中，分片集群的配置服务器可以部署为副本集。副本集的配置服务器必须运行WiredTiger 存储引擎。单一的分片集群必须独占使用其配置服务器。如果您有多个分片集群，每个集群必须拥有专有的的副本集配置服务器。

**两个或更多副本集作为分片服务器：** 这些副本集是碎片。随后会详细介绍如何创建副本集。

**一个或多个查询路由器(mongos)：** mongos实例是为集群的路由器。通常情况下，每个应用服务器需要部署一个mongos实例。
也可以部署一组的mongos实例并在应用和mongos之间采用代理/负载均衡器。在这些部署中，您必须配置负载平衡器客户端的相似性，以便从单个客户端的每个连接都能指向相同的mongos。因为游标和其他资源是特定于单个mongos实例的，每个客户端只能与同一个mongos实例进行交互。