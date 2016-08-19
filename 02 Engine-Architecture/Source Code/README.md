### 源码包结构

```
com
└── xyt
    ├── app
    │   ├── develop
    │   │   └── action
    │   └── system
    │       └── action
    ├── components
    │   ├── message
    │   │   ├── client
    │   │   ├── mail
    │   │   └── sms
    │   └── storage
    │       ├── mongo
    │       └── qiniu
    ├── config
    │   └── filter
    ├── modules
    │   ├── auth
    │   ├── bridge
    │   │   └── workflow
    │   │       └── param
    │   ├── ead
    │   │   ├── dao
    │   │   │   └── base
    │   │   ├── entity
    │   │   ├── service
    │   │   │   └── impl
    │   │   └── utils
    │   ├── engine
    │   │   ├── collection
    │   │   │   ├── base
    │   │   │   ├── parser
    │   │   │   └── query
    │   │   │       ├── driver
    │   │   │       ├── mongo
    │   │   │       └── rdb
    │   │   ├── config
    │   │   ├── driver
    │   │   ├── message
    │   │   ├── model
    │   │   │   ├── convertor
    │   │   │   ├── type
    │   │   │   └── validator
    │   │   ├── utils
    │   │   ├── variable
    │   │   └── view
    │   │       ├── action
    │   │       ├── base
    │   │       ├── box
    │   │       │   └── service
    │   │       ├── builder
    │   │       ├── example
    │   │       ├── helper
    │   │       ├── page
    │   │       ├── report
    │   │       └── standard
    │   ├── exception
    │   ├── notice
    │   │   ├── entity
    │   │   ├── parser
    │   │   ├── service
    │   │   │   └── impl
    │   │   └── task
    │   ├── sys
    │   │   ├── dao
    │   │   ├── entity
    │   │   └── service
    │   │       └── impl
    │   └── workflow
    │       ├── dao
    │       ├── entity
    │       ├── service
    │       │   └── impl
    │       └── utils
    ├── plugins
    │   └── cache
    ├── router
    │   └── render
    └── utils
```

- `app/` 应用自定义Action
- `app/develop/` 开发者中心应用自定义Action
- `app/system/` 系统管理模块自定义Action
- `components/` 组件包
- `components/message/` 消息组件
- `components/storage/` 存储组件
- `config/` 配置
- `config/filter/` 路由配置
- `modules/` 模块
- `modules/auth/` 认证模块
- `modules/bridge/` 桥模块
- `modules/ead/` EAD配置管理
- `modules/engine/` EAD引擎
- `modules/engine/collection/` 集合模块
- `modules/engine/config/` EAD引擎配置
- `modules/engine/driver/` 驱动
- `modules/engine/message/` 消息
- `modules/engine/model/` 模型
- `modules/engine/utils/` 引擎工具包
- `modules/engine/variable/` 变量
- `modules/engine/view/` 模型
- `modules/exception/` 异常
- `modules/notice/` 通知
- `modules/sys/` 系统管理
- `modules/workflow/` 工作流
- `plugins/` 插件
- `router/` 路由
- `utils/` 工具类
