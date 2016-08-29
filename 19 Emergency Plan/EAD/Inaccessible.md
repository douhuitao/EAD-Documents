## 系统无法访问及解决方案

当 EAD 系统无法访问时，需要首先确认是网络无法访问还是应用服务无响应造成的无法访问，尽快定位访问故障原因，通知相关人员恢复故障。

### 网络无法访问

使用访问异常终端设备使用命令行窗口 Ping 命令确认是否可以正确访问应用服务器，命令如下：
```
ping eas.whchem.com
```

如果 Ping 命令返回如下记录，说明终端设备到应用服务器网络正常。
```
64 bytes from 122.5.25.240: icmp_seq=0 ttl=243 time=68.195 ms
64 bytes from 122.5.25.240: icmp_seq=1 ttl=243 time=70.153 ms
64 bytes from 122.5.25.240: icmp_seq=2 ttl=243 time=73.507 ms
64 bytes from 122.5.25.240: icmp_seq=3 ttl=243 time=71.101 ms
64 bytes from 122.5.25.240: icmp_seq=4 ttl=243 time=70.941 ms
--- eas.whchem.com ping statistics ---
11 packets transmitted, 10 packets received, 9.1% packet loss
round-trip min/avg/max/stddev = 68.195/71.639/75.254/1.904 ms
```

如果 Ping 命令返回如下记录，说明终端设备到应用服务器网络连接超时。
```
Request timeout for icmp_seq 0
Request timeout for icmp_seq 1
Request timeout for icmp_seq 2
Request timeout for icmp_seq 3
Request timeout for icmp_seq 4
Request timeout for icmp_seq 5
--- eas.whchem.com ping statistics ---
7 packets transmitted, 0 packets received, 100.0% packet loss
```

网络连接超时请使用其它设备或让处于其它网络环境的人员按照如上办法继续确认与应用服务器网络是否连通。

确认网络访问情况后与应用服务器管理员和网络管理员联系确认服务器故障或网络故障问题。

### 应用服务无响应

如果确认与应用服务器网络访问正常，应用服务器处于正常的启动状态，但是系统仍无法访问，通知应用服务管理员通过远程连接登录应用服务器查看服务进程或查看 Tomcat 日志确认 EAD 应用服务启停状态。根据排查情况重启 EAD 应用服务。


