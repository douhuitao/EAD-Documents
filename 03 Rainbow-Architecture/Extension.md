## 扩展支持

### AMD 模块定义

```
define(function(require, exports, module){
    var fn = function(){

    };

    return fn;
});
```

API 参考：http://requirejs.org/docs/api.html#cjsmodule

### 视图扩展

扩展脚本存放路径，```/js/view/extend-exsamp.js```，在开发者中心配置视图扩展为“extend-exsamp”会自动加载该扩展并应用执行。

### 动作扩展

扩展脚本存放路径，```/js/action/extend-exsamp.js```，在开发者中心配置动作事件为“e.extend-exsamp”会自动加载该扩展并应用执行。