# npm 常用命令

## 安装

```bash
# 本地安装
npm install eslint

# 全局安装
npm install -g eslint

# 使用别名 i
npm i eslint

# 同时安装多个模块
npm i eslint eslint-plugin-vue eslint-config-vue

# 安装package.json里dependencies和devDependencies记录的所有依赖包
npm install
```

## 初始化

```bash
npm init
```

执行以上命令将会在工程目录创建文件`package.json`，用于描述整个npm工程，例：

```json
{
  "name": "hello-world",
  "description": "",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "https://git.oschina.net/chenjianlong/hello-world.git"
  },
  "keywords": [],
  "author": "",
  "license": "MIT",
  "dependencies": {
    "jroll": "^2.4.5", 
    "vue": "^2.2.1"
  },
  "devDependencies": {
    "eslint": "^3.9.1",
    "eslint-config-vue": "^2.0.0",
    "eslint-plugin-vue": "^1.0.0",
    "jtaro-bundle": "^0.1.1",
    "jtaro-module": "^0.1.0"
  }
}
```

- **name** 项目名称
- **description** 项目描述
- **version** 版本号
- **main** 入口文件，其它项目将该项目当模块引入时的默认入口，例：该项目名称为abc，引入它的项目执行`require('abc')`时默认返回该入口文件，前提是该abc项目必须先使用`npm publish`发布或`npm link`关联
- **scripts** 脚本命令，使用`npm run <命令>`执行，例：`npm run test`将会输出`Error: no test specified`
- **repository** git仓库
- **keywords** 关键字，用于供给npmjs网站搜索
- **author** 作者
- **license** 协议
- **dependencies** 依赖，使用`npm i --save <模块包>`选项安装的模块包将会记录在这里，`--save`的别名是`-S`
- **devDependencies** 开发依赖，使用`npm i --save-dev <模块包>`选项安装的模块包将会记录在这里，`--save-dev`的别名是`-D`

更多内容请访问：[https://docs.npmjs.com/](https://docs.npmjs.com/)