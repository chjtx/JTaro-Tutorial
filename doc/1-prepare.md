# 准备工作

## 安装工具

- [VSCode (Visual Studio Code)](http://www.vscode.org/) 代码编辑器
- [Nodejs](http://nodejs.cn/) 开发运行环境
- [Git](https://git-scm.com/) 分布式版本控制系统，管理代码仓库
- [ESlint](http://eslint.org/) 代码校验工具

VSCode、Nodejs、Git的安装比较简单，直接去下载安装即可，ESlint需要先安装完Nodejs然后在命令行（终端）运行以下命令安装

```bash
npm install -g eslint
```

## 创建工程

### 步骤一、找个代码托管平台

- [GitHub](https://github.com/) 一个面向开源及私有软件项目的托管平台，私有库收费
- [码云](https://git.oschina.net/) 开源中国社区团队推出的基于Git的快速的、免费的、稳定的在线代码托管平台，不限制私有库和公有库数量

以上两个都是使用git协议的代码托管平台，还有很多类似这样的平台，这里不一一列举。GitHub是全球最大的社交编程及代码托管网站，有很多很优秀的项目在上面开源共享，但在国内访问有点慢，所以我们选择码云

- 在[码云](https://git.oschina.net/) https://git.oschina.net/ 注册帐号
- 新建项目，`是否公开`选择私有，demo项目就不必要公开了

### 步骤二、新建工程

- `克隆/下载`复制地址
- 用npm命令初始化工程

```
npm init
```

创建目录

```c
/-- dev
    `-- assets/  // 存放静态资源
    `-- data/    // 存放模拟数据
    `-- pages/   // 存放业务逻辑
    `-- vendors/ // 存放第三方库
    `-- index.html // 首页
```

### 步骤三、安装开发所需文件

1. 下载框架文件

- [Vue](http://cn.vuejs.org/v2/guide/installation.html) 一套构建用户界面的渐进式前端MVVM框架
- [JRoll](http://www.chjtx.com/JRoll/#download) 一款具有滑动加速、回弹、缩放、滚动条、滑动事件等功能的html5滚动插件
- [JTaro](http://www.chjtx.com/JTaro/) 基于Vue2.0开发的轻量级SPA（单页应用）框架

分别到以上三个网站下载最新的代码（包括带.min后缀的压缩版）

2. 安装开发工具

- [JTaro Module](https://github.com/chjtx/JTaro-Module) 一款使用ES6模块语法的前端模块管理工具
- [JTaro Bundle](https://github.com/chjtx/JTaro-Bundle) 为JTaro服务的打包脚本

```
npm i -D jtaro-module jtaro-bundle
```

3. 安装eslint到本地项目

使用vue代码规范的配置，Mac需要加sudo提升权限安装

```
sudo npm i -D eslint eslint-plugin-vue eslint-config-vue
```

VSCode编辑器安装也需要安装eslint扩展


