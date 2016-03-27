## 生成工具

![生成工具](..\images\package-generated.png)

### Node.js
Node.js是一个基于Chrome JavaScript运行时建立的平台， 用于方便地搭建响应速度快、易于扩展的网络应用。Node.js 使用事件驱动， 非阻塞I/O 模型而得以轻量和高效，非常适合在分布式设备上运行的数据密集型的实时应用。

登录官方主页，https://nodejs.org/ 选择合适的版本下载并安装。

### LESS
LESS 做为 CSS 的一种形式的扩展，它并没有减少 CSS 的功能，而是在现有的 CSS 语法之上，添加了许多其它的功能。LESS 通过变量、混合、嵌套规则、函数与计算实现 CSS 的模块化配置开发。

工具安装
```
npm install lessc -g
```

打包命令（依赖于 Node 环境）
```
lessc style.less style.css
```

### Requirejs

```r.js``` 下载地址：http://requirejs.org/docs/release/2.2.0/r.js ，（另存为链接，下载存储到 Rainbow 根目录）。

Rainbow 根目录，执行打包命令（依赖于 Node 环境）。
```
node r.js -o _built.js
```