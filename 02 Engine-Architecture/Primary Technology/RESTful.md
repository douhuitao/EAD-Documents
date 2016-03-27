### RESTful 解释

**REST**具象状态传输（英文：Representational State Transfer，简称REST）是Roy Thomas Fielding博士于2000年在他的博士论文 "Architectural Styles and the Design of Network-based Software Architectures" 中提出来的一种万维网软件架构风格。

目前在三种主流的Web服务实现方案中，因为REST模式与复杂的SOAP和XML-RPC相比更加简洁，越来越多的web服务开始采用REST风格设计和实现。例如，Amazon.com提供接近REST风格的Web服务进行图书查找；雅虎提供的Web服务也是REST风格的。

### RESTful 要点及标准

需要注意的是，REST是设计风格而不是标准。REST通常基于使用HTTP，URI，和XML以及HTML这些现有的广泛流行的协议和标准。

- 资源是由URI来指定。
- 对资源的操作包括获取、创建、修改和删除资源，这些操作正好对应HTTP协议提供的GET、POST、PUT和DELETE方法。
- 通过操作资源的表现形式来操作资源。
- 资源的表现形式则是XML或者HTML，取决于读者是机器还是人，是消费web服务的客户软件还是web浏览器。当然也可以是任何其他的格式。

#### REST的要求

- 客户端和服务器结构
- 连接协议具有无状态性
- 能够利用Cache机制增进性能
- 一致性的操作界面
- 层次化的系统
- 所需代码 - Javascript（可选）

#### 关于状态

应该注意区别应用的状态和连接协议的状态。HTTP连接是无状态的（也就是不记录每个连接的信息），而REST传输会包含应用的所有状态信息，因此可以大幅降低对HTTP连接的重复请求资源消耗。

#### 应用于Web服务

符合REST设计风格的Web API称为RESTful API。它从以下三个方面资源进行定义：

- 直观简短的资源地址：URI，比如：http://example.com/resources/。
- 传输的资源：Web服务接受与返回的互联网媒体类型，比如：JSON，XML，YAML等。
- 对资源的操作：Web服务在该资源上所支持的一系列请求方法（比如：POST，GET，PUT或DELETE）。

下表列出了在实现RESTful API时HTTP请求方法的典型用途。

HTTP请求方法在RESTful API中的典型应用

| 资源 | GET | PUT | POST | DELETE |
| --- | --- | --- | ---- | ------ |
| URI：http://example.com/resources/	 | 列出URI，以及该资源组中每个资源的详细信息（后者可选）| 使用给定的一组资源替换当前整组资源 | 在本组资源中创建/追加一个新的资源。该操作往往返回新资源的URL | 删除整组资源 | 
| URI：http://example.com/resources/142	| 获取指定的资源的详细信息，格式可以自选一个合适的网络媒体类型（比如：XML、JSON等） | 替换/创建指定的资源。并将其追加到相应的资源组中 | 把指定的资源当做一个资源组，并在其下创建/追加一个新的元素，使其隶属于当前资源 | 删除指定的元素 |

PUT和DELETE方法是幂等方法。GET方法是安全方法（不会对服务器端有修改，因此当然也是幂等的）。

> 不像基于SOAP的Web服务，RESTful Web服务并没有“正式”的标准。这是因为REST是一种架构，而SOAP只是一个协议。虽然REST不是一个标准，但大部分RESTful Web服务实现会使用HTTP、URI、JSON和XML等各种标准。


### REST的优点

- 可更高效利用缓存来提高响应速度
- 通讯本身的无状态性可以让不同的服务器的处理一系列请求中的不同请求，提高服务器的扩展性
- 浏览器即可作为客户端，简化软件需求
- 相对于其他叠加在HTTP协议之上的机制，REST的软件依赖性更小
- 不需要额外的资源发现机制
- 在软件技术演进中的长期的兼容性更好

