## 主题自定义

主题模板包主要有样式文件和模板文件组成，可以根据基础样式文件扩展开发不同风格的样式文件，在应用定义时可以选择配置当前主题的不同样式风格。

### 主题包结构

- **less/**, less、CSS 样式文件存放目录; 
- **destop.html**, 模板文件;

### 模板开发示例

#### 面包屑条目模板（tpl-breadcurm）

```
<script type="text/template" id="tpl-breadcurm-item">
  <button type="button" class="btn btn-primary">
    <span class="glyphicon glyphicon-th"></span>
  </button>
</script>
```


#### 模板组件

使用 ```script``` 标签包裹模板代码，设置 ```type``` 属性为 ```text/template```,```id``` 为模板名称，在 Rianbow 开发中通过 DOM id 调用。

```
<script type="text/template" id="tpl-breadcurm-item">
  ……
</script>
```

#### 命名

设置模板模块的 DOM id 以“tpl-” 开头，例如“tpl-breadcurm-item”。

### 创建或发布主题

主题存放在 Rianbow 工程的 “theme” 目录下。

0. 在主题存放目录建立主题包目录，目录名即是主题的标识名称;
0. 在新建的主题包下创建样式文件包和模板文件。