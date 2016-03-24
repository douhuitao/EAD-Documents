## 全局对象

### Rainbow

源码位置：```/src/base/app.js```,全局命名空间 ```rainbow```。

属性读取示例:
```
var url = rainbow.baseUrl + '/res-path';
```

方法读取示例:
```
var msg = 'content';
rianbow.alert(msg);
```

#### 属性

**baseUrl** : 当前应用 API 根路径。

**LANG** : Rainbow 全局语言包对象，语言包存储位置 ```/nls/```，命名空间参考```/nls/en/rainbow.js```，调用方式，例如： ```rainbow.LANG.__form.done```。

**sign** : 用户签到模块引用，具体方法参考```/src/common/sign.js```;

**layout** : 应用布局实例,支持 load 和 render 方法,

#### 方法

### Underscore

### jQuery

### Backbone