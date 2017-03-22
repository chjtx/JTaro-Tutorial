# 开发

## 开发之前

Vue 中文网：[http://cn.vuejs.org/](http://cn.vuejs.org/)

JRoll 官网：[http://www.chjtx.com/JRoll/](http://www.chjtx.com/JRoll/)

JTaro 官网：[http://www.chjtx.com/JTaro/](http://www.chjtx.com/JTaro/)

JTaro Module：[https://github.com/chjtx/JTaro-Module](https://github.com/chjtx/JTaro-Module)

Git中文教程：[http://git.oschina.net/progit/](http://git.oschina.net/progit/)

## 创建开发分支

创建一条develop分支用于开发，master主干保留用于生产上线

```bash
git checkout -b develop
```

## 开发页面

### index.html

- 创建index.html
- 拷贝jtaro-module的文件到dev/jtaro-module文件夹里，方便克隆项目不需要安装npm依赖包也能正常运行

- 配置package.json的npm运行脚本命令

```json
"scripts": {
  "dev": "cd dev && node jtaro-module/server.js"
}
```

- 运行

```bash
npm run dev
```

### home列表页

- 创建home.js、home.html，home.js符合vue组件格式
- 创建假数据data/list.json
- 使用api.js，方便切换开发环境和生产环境
- 使用[axios](https://github.com/mzabriskie/axios)获取数据
- 安装[promise-polyfill](https://github.com/taylorhakes/promise-polyfill)使旧浏览器支持Promise
- 使用[jroll-infinite](https://github.com/chjtx/JRoll/tree/master/extends/jroll-vue-infinite)展示数据

### detail详细页

- 创建detail.js、detail.html
- 开发header组件
- 从[阿里巴巴矢量图标库](http://www.iconfont.cn/)下载需要的图标
- 创建假数据data/detail_x.json
- 编辑afterEnter路由勾子读取数据
- 开发分享组件
- 开发评论组件

### reply评论面

- 复用detail页的组件

## 提交代码

VSCode左侧git选项，添加备注，提交
