### Mysql 优化配置

Mysql 安装完成后，若安装时的配置不能满足实际的使用需求，则需要在 Mysql 配置文件中进行重新配置；

配置文件在 Mysql 安装目录下：`my.ini`;

### my.ini 配置

```
[mysqld]
port = 3306
serverid = 1
socket = /tmp/mysql.sock
skip-locking # 避免MySQL的外部锁定，减少出错几率增强稳定性。
```

```
skip-name-resolve
```
禁止MySQL对外部连接进行DNS解析，使用这一选项可以消除MySQL进行DNS解析的时间。但需要注意，如果开启该选项，则所有远程主机连接授权都要使用IP地址方式，否则MySQL将无法正常处理连接请求!

```
back_log = 500
```
要求 MySQL 能有的连接数量。当主要MySQL线程在一个很短时间内得到非常多的连接请求，这就起作用，然后主线程花些时间(尽管很短)检查连接并且启动一个新线程。
back_log值指出在MySQL暂时停止回答新请求之前的短时间内多少个请求可以被存在堆栈中。只有如果期望在一个短时间内有很多连接，你需要增加它，换句话说，这值对到来的TCP/IP连接的侦听队列的大小。你的操作系统在这个队列大小上有它自己的限制。试图设定back_log高于你的操作系统的限制将是无效的。当你观察你的主机进程列表，发现大量 264084 | unauthenticated user | xxx.xxx.xxx.xxx | NULL | Connect | NULL | login | NULL 的待连接进程时，就要加大 back_log 的值了。默认数值是50，我把它改为500。

```
key_buffer_size = 384M
```
key_buffer_size指定用于索引的缓冲区大小，增加它可得到更好处理的索引(对所有读和多重写)，到你能负担得起那样多。如果你使它太大，系统将开始换页并且真的变慢了。对于内存在4GB左右的服务器该参数可设置为384M或512M。通过检查状态值Key_read_requests和 Key_reads,可以知道key_buffer_size设置是否合理。比例key_reads / key_read_requests应该尽可能的低，至少是1:100，1:1000更好(上述状态值可以使用SHOW STATUS LIKE ‘key_read%'获得)。注意：该参数值设置的过大反而会是服务器整体效率降低!

```
max_allowed_packet = 32M
```
增加该变量的值十分安全，这是因为仅当需要时才会分配额外内存。例如，仅当你发出长查询或mysqld必须返回大的结果行时mysqld才会分配更多内存。该变量之所以取较小默认值是一种预防措施，以捕获客户端和服务器之间的错误信息包，并确保不会因偶然使用大的信息包而导致内存溢出。

```
table_cache = 512
```
table_cache指定表高速缓存的大小。每当MySQL访问一个表时，如果在表缓冲区中还有空间，该表就被打开并放入其中，这样可以更快地访问表内容。通过检查峰值时间的状态值Open_tables和Opened_tables，可以决定是否需要增加table_cache的值。如果你发现 open_tables等于table_cache，并且opened_tables在不断增长，那么你就需要增加table_cache的值了(上述状态值可以使用SHOW STATUS LIKE ‘Open%tables'获得)。注意，不能盲目地把table_cache设置成很大的值。如果设置得太高，可能会造成文件描述符不足，从而造成性能不稳定或者连接失败。

```
sort_buffer_size = 4M
```
查询排序时所能使用的缓冲区大小。注意：该参数对应的分配内存是每连接独占!如果有100个连接，那么实际分配的总共排序缓冲区大小为100 × 4 = 400MB。所以，对于内存在4GB左右的服务器推荐设置为4-8M。

```
read_buffer_size = 4M
```
读查询操作所能使用的缓冲区大小。和sort_buffer_size一样，该参数对应的分配内存也是每连接独享!

```
join_buffer_size = 8M
```
联合查询操作所能使用的缓冲区大小，和sort_buffer_size一样，该参数对应的分配内存也是每连接独享!

```
myisam_sort_buffer_size = 64M
```
MyISAM表发生变化时重新排序所需的缓冲

```
query_cache_size = 64M
```
指定MySQL查询缓冲区的大小。可以通过在MySQL控制台执行以下命令观察：
```
# > SHOW VARIABLES LIKE ‘%query_cache%'; 
# > SHOW STATUS LIKE ‘Qcache%'; # 如果Qcache_lowmem_prunes的值非常大，则表明经常出现缓冲不够的情况;
```
如果Qcache_hits的值非常大，则表明查询缓冲使用非常频繁，如果该值较小反而会影响效率，那么可以考虑不用查询缓冲;Qcache_free_blocks，如果该值非常大，则表明缓冲区中碎片很多。

```
thread_cache_size = 64
```
可以复用的保存在中的线程的数量。如果有，新的线程从缓存中取得，当断开连接的时候如果有空间，客户的线置在缓存中。如果有很多新的线程，为了提高性能可以这个变量值。通过比较 Connections 和 Threads_created 状态的变量，可以看到这个变量的作用

```
tmp_table_size = 256M
max_connections = 1000
```
指定MySQL允许的最大连接进程数。如果在访问论坛时经常出现Too Many Connections的错误提示，则需要增大该参数值。

```
max_connect_errors = 10000000
```
对于同一主机，如果有超出该参数值个数的中断错误连接，则该主机将被禁止连接。如需对该主机进行解禁，执行：`FLUSH HOST`;。

```
wait_timeout = 10
```
指定一个请求的最大连接时间，对于4GB左右内存的服务器可以设置为5-10。

```
thread_concurrency = 8
```
该参数取值为服务器逻辑CPU数量×2，在本例中，服务器有2颗物理CPU，而每颗物理CPU又支持H.T超线程，所以实际取值为4 × 2 = 8

```
skip-networking
```
开启该选项可以彻底关闭MySQL的TCP/IP连接方式，如果WEB服务器是以远程连接的方式访问MySQL数据库服务器则不要开启该选项!否则将无法正常连接!

```
long_query_time = 10
log-slow-queries =
log-queries-not-using-indexes
```
开启慢查询日志( slow query log )
慢查询日志对于跟踪有问题的查询非常有用。它记录所有查过long_query_time的查询，如果需要，还可以记录不使用索引的记录。下面是一个慢查询日志的例子：
开启慢查询日志，需要设置参数log_slow_queries、long_query_times、log-queries-not-using-indexes。
log_slow_queries指定日志文件，如果不提供文件名，MySQL将自己产生缺省文件名。long_query_times指定慢查询的阈值，缺省是10秒。log-queries-not-using-indexes是4.1.0以后引入的参数，它指示记录不使用索引的查询。设置 long_query_time=10

### 附录命令

使用show status命令查看mysql状态相关的值及其含义：
使用show status命令，含义如下:
- aborted_clients 客户端非法中断连接次数
- aborted_connects 连接mysql失败次数
- com_xxx xxx命令执行次数,有很多条
- connections 连接mysql的数量
- Created_tmp_disk_tables 在磁盘上创建的临时表
- Created_tmp_tables 在内存里创建的临时表
- Created_tmp_files 临时文件数
- Key_read_requests The number of requests to read a key block from the cache
- Key_reads The number of physical reads of a key block from disk
- Max_used_connections 同时使用的连接数
- Open_tables 开放的表
- Open_files 开放的文件
- Opened_tables 打开的表
- Questions 提交到server的查询数
- Sort_merge_passes 如果这个值很大,应该增加 my.ini 中的sort_buffer值
- Uptime 服务器已经工作的秒数

### 提升性能的建议

- 如果 opened_tables 太大,应该把 my.ini 中的 table_cache 变大
- 如果 Key_reads 太大,则应该把 my.ini 中 key_buffer_size 变大.可以用 Key_reads/Key_read_requests 计算出 cache 失败率
- 如果 Handler_read_rnd 太大,则你写的 SQL 语句里很多查询都是要扫描整个表,而没有发挥索引的键的作用
- 如果 Threads_created 太大,就要增加 my.ini 中 thread_cache_size 的值.可以用 Threads_created/Connections 计算 cache 命中率
- 如果 Created_tmp_disk_tables 太大,就要增加 my.ini 中 tmp_table_size 的值,用基于内存的临时表代替基于磁盘的

### 其他内容

存储引擎是什么？MySQL中的数据用各种不同的技术存储在文件(或者内 正确的编译方法固然重要，但它只是提高MySQL服务器性能工作的一部分。MySQL服务器的许多参数会影响服务器的性能表现，而且我们可以把这些参数保存到配置文件，使得每次MySQL服务器启动时这些参数都自动发挥作用。这个配置文件就是 my.ini。
MySQL服务器提供了 my.ini 文件的几个示例，它们可以在 Mysql 安装目录下找到，名字分别为 my-small.ini、my-medium.ini、my-large.ini 以及my-huge.ini。文件名字中关于规模的说明描述了该配置文件适用的系统类型。例如，如果运行MySQL服务器的系统内存不多，而且MySQL只是偶尔使用，那么使用my-small.ini 配置文件最为理想，这个配置文件告诉mysqld daemon使用最少的系统资源。反之，如果MySQL服务器用于支持一个大规模的在线商场，系统拥有2G的内存，那么使用mysql-huge.ini 最为合适。
要使用上述示例配置文件，我们应该先复制一个最适合要求的配置文件，并把它命名为 my.ini 。这个复制得到的配置文件可以按照如下三种方式使用：

- 全局：把这个 my.ini 文件复制到服务器的/etc目录，此时文件中所定义的参数将全局有效，即对该服务器上运行的所有MySQL数据库服务器都有效。
- 局部：把这个 my.ini 文件复制到 Mysql 安装目录下将使该文件只对指定的服务器有效。
- 用户：最后，我们还可以把该文件的作用范围局限到指定的用户，这只需把 my.ini 文件复制到用户的根目录即可。

那么，如何设置my.ini文件中的参数呢？或者进一步说，哪些参数是我们可以设置的呢？所有这些参数都对MySQL服务器有着全局性的影响，但同时每一个参数都和 MySQL 的特定部分关系较为密切。例如，max_connections 参数属于 mysqld 一类。那么，如何才能得知这一点呢？这只需执行如下命令：

```
$ mysqld –help
```
该命令将显示出和mysqld有关的各种选项和参数。要寻找这些参数非常方便，因为这些参数都在“Possible variables for option –set-variable (-O) are”这行内容的后面。找到这些参数之后，我们就可以在my.ini文件中按照如下方式设置所有这些参数：

```
set-variable = max_connections=100
```

这行代码的效果是：同时连接MySQL服务器的最大连接数量限制为100。不要忘了在my.ini文件[mysqld]小节加上一个set-variable指令，具体请参见配置文件中的示例。

