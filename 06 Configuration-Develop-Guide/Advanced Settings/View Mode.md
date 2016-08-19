## 视图详情模式

EAD 平台支持对单条数据详情访问模式进行设置，针对多个子视图的视图支持直接在详情页面进行子视图数据预览和编辑。

### 类型说明

#### 选项卡

mode 参数选项：```tab```

![PNG](..\images\advanced\view-detail-tab.png)

#### 页面 (page)

mode 参数选项：```page```

![PNG](..\images\advanced\view-detail-page.png)

### 视图前端参数设置

```
{
  "detail":{
    "mode":"page"
  }
}
```

> 视图详细模式默认值为 “tab”。