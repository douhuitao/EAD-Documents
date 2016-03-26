## Rainbow 扩展开发

### 技术储备

开发者需要熟练掌握 HTML 5 相关网页前端知识，了解基于 AMD 规范的 Requirejs 模块管理库。有一定 MVC 或 MVVM 的设计思想知识储备，熟练掌握 Backbone 、 jQuery 等 Rainbow 依赖的核心类库。

### 开发概述

本章节描述了扩展开发 Rainbow 必须了解的依赖和规范。分别介绍了 Rainbow 框架的全局对象，描述了动作和视图扩展开发的规范，示例描述了通用视图、表单控件、主题的自定义方法。

### AMD 模块定义

Rainbow 的源码组织完全遵循 AMD 规范，无论是驱动扩展还是通用组件开发必须熟练掌握 AMD 模块定义规范。

```
define(function(require, exports, module){
    var fn = function(){

    };

    return fn;
});
```

API 参考：http://requirejs.org/docs/api.html#cjsmodule