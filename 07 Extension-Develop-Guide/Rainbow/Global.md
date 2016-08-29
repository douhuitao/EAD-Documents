## 全局对象

### Rainbow

源码位置：```/src/base/app.js```,全局命名空间 ```rainbow```。

属性读取示例:
```
var url = rainbow.baseUrl + '/res-path';
```

方法调用示例:
```
var msg = 'content';
rianbow.alert(msg);
```

#### 属性

**baseUrl** : 当前应用 API 根路径。

**LANG** : Rainbow 全局语言包对象，语言包存储位置 ```/nls/```，命名空间参考```/nls/en/rainbow.js```，调用方式，例如： ```rainbow.LANG.__form.done```。

**sign** : 用户签到模块引用，具体方法参考 ```/src/common/sign.js```。

**layout** : 应用布局实例,支持加载 (load) 和渲染 (render) 方法，具体方法参考 ```/src/base/app.js```。

**router** : 应用路由实例，详情参考 Backbone.Router 对象。

**current** : 当前活动视图对象实例。

#### 方法

**alert** : 自定义提醒。

```
rainbow.alert(msg);
```

**errorMsg** : 错误提醒。

```
rainbow.errorMsg(msg);
```

**successMsg** : 成功提醒。

```
rainbow.successMsg(msg);
```

**confirm** : 确认提醒。

```
rainbow.confirm = function(msg)
```


### Underscore

Rainbow 容器内初始化内置了 Underscore 库，在容器作用域内可以通过 ```_``` 命名空间访问和调用 Underscore 的所有对象及方法。

API 参考：http://underscorejs.org/

### jQuery

Rainbow 容器内初始化内置了 jQuery 库，在容器作用域内可以通过 ```$``` 或 ```jQuery``` 命名空间访问和调用 jQuery 的所有对象及方法。

API 参考：http://jquery.com/

### Backbone

Rainbow 容器内初始化内置了 Backbone 库，在容器作用域内可以通过 ```Backbone``` 命名空间访问和调用 Backbone 的所有对象及方法。

API 参考：http://backbonejs.org/