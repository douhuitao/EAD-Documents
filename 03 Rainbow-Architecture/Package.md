## 源码包结构

```
├─assets
│  ├─bootstrap
│  ├─css
│  ├─fonts
│  └─img
├─dist
│  └─js
├─js
│  ├─action
│  ├─vendor
│  │  ├─bootstrap-daterangepicker
│  │  ├─bootstrap-datetimepicker
│  │  ├─highlight
│  │  ├─jquery
│  │  ├─kindeditor-4.1.9
│  │  ├─requirejs
│  │  ├─select2-4.0.0
│  │  ├─soundmanager
│  │  ├─sweetalert
│  │  └─webuploader-0.1.5
│  └─view
├─nls
│  ├─en
│  └─zh
├─src
│  ├─base
│  ├─common
│  ├─components
│  │  ├─base
│  │  ├─controls
│  │  ├─editor
│  │  ├─form
│  │  ├─list
│  │  └─webkit
│  ├─utility
│  └─view
│      └─kit
│         └─action
└─theme
    ├─classic
    └─tech
```

- assets  //资源包
    - bootstrap //Bootstrap
    - css //CSS 样式文件
    - fonts // 字体
    - img //图片
- dist
    - js // 打包 JS 生成目录
- js
    - action //扩展 Action 存放路径
    - vendor //第三方组件目录
      - bootstrap-daterangepicker //日期区间选择器
      - bootstrap-datetimepicker //日期选择器
      - highlight //代码高亮
      - jquery //jQuery
      - kindeditor-4.1.9 //富文本编辑器
      - requirejs //AMD 加载器
      - select2-4.0.0 //增强选择器表单控件
      - soundmanager //声音播放
      - sweetalert //消息提示
      - webuploader-0.1.5 //Web 上传组件
    - view //扩展视图存放路径
- nls //语言包
    - en //英文语言包目录
    - zh //中文语言包目录
- src //源码目录
    - base //基础模块
    - common //通用模块
    - components //组件
      - base //基础抽象
      - controls //表单控件
      - editor //富交互编辑器
      - form //表单
      - list //列表
      - webkit //小组件
    - utility //辅助函数
    - view //视图
      - kit //部件
          - action //视图动作
- theme //主题包存放路径
    - classic //经典主题
    - tech //科技主题