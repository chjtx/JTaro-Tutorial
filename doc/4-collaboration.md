# 协作开发

此处只讨论使用 `JTaro Module` 搭建项目的多人协作开发模式

## 角色

- `架构师`，负责搭建整个项目框架，功能组件开发，技术指导
- `开发组长`，负责任务分配，页面组件开发，代码合并
- `开发组员`，负责业务逻辑开发，业务需求跟进
- `设计师`，负责UI设计，字体图标设计

以上角色仅与前端开发相关，后端、运维、需求、业务等等本文不作讨论

## 项目结构（参考一）

参考示例：[http://git.oschina.net/chenjianlong/hello-world](http://git.oschina.net/chenjianlong/hello-world)

```js
/                          //根目录
|-- dev/                    //开发目录
    |-- assets/             //资源目录（设计师）
        |-- fonts/
            |-- ...
        |-- images/
            |-- ...
    |-- data/               //开发时用的模拟数据（开发组长）
        |-- ...
    |-- jtaro-module/       //（架构师）
        |-- ...
    |-- api/
        |-- api.js          //用于切换开发环境和生产环境的接口（架构师）
        |-- api4dev.js      //开发用的接口（开发组长）
        |-- api4pro.js      //生产用的接口（开发组长）
    |-- components/         //业务无关的通用组件（架构师）
        |-- dialog.html
        |-- dialog.js
        |-- ...
    |-- pages/
        |-- page1.html      //业务页面文件（开发组员）
        |-- page1.js        //业务逻辑文件（开发组员）
        |-- ...
        |-- components/     //业务相关的个性组件（开发组长）
            |-- shoppingCar.html
            |-- shoppingCar.js
            |-- ...
    |-- vendors/            //第三方工具库（架构师 && 开发组长）
        |-- vue.js
        |-- vue.min.js
        |-- ...
    |-- index.html          //首页（架构师）

|-- pro                     //生产目录（架构师）
    |-- assets/
        |-- ...
    |-- vendors/
        |-- ...
    |-- pages.js
    |-- index.html          //生产首页

|-- build.js                //将开发代码构建成生产代码的脚本
```

- 以上目录结构基本满足各种中小型项目，大型项目（由多个小型项目构成）也适用，当然，实际应用的目录结构远比这里复杂
- 以上目录结构与参考项目有些少区别，基本分工理念一致
- 将`node_modules`的文件拷贝到`vendors`和`jtaro-module`目录的目的在于方便克隆项目

## 项目结构（参考二）

参考示例：[https://github.com/chjtx/JTaro-UI](https://github.com/chjtx/JTaro-UI)

```js
/
|-- pages/
    |-- button.html
    |-- button.js
    |-- ...
|-- components/
    |-- loader.html
    |-- loader.js
    |-- ...
|-- build/
    |-- assets/
    |-- vendors/
    |-- pages.js
    |-- index.html
|-- node_modules/
|-- index.html
|-- build.js
```

该目录结构与`项目结构（参考一）`的主要区别在于直接将工程根目录作为开发目录，另外创建`build`目录作为生产目录，这样做的

好处：

- 可以直接调用`node_modules`目录里的组件，无需额外拷贝

弊端：

- 当开发所需的目录越来越多时，会导致整个工程结构看起来混乱不堪

## 仓库分支

1. `develop`，开发分支，尽可能只修改开发相关代码，如`项目结构（参考一）`，只在该分支修改`dev`目录的内容，避免与生产分支发生冲突

2. `master`，生产分支，尽可能只修改生产相关代码，如`项目结构（参考一）`，只在该分支处理`pro`目录、`build.js`、`dev/api/api.js`

在实际项目开发中，这两个只是主要分支，在`develop`分支下还有很多bug分支、需求分支、紧急bug修复分支等等，这些小分支由开发组员维护，当功能完成或bug修复后由开发组长合并到`develop`分支，当项目开发到一定阶段可以投放到生产时由架构师或项目负责人将`develop`分支合并到`master`分支
