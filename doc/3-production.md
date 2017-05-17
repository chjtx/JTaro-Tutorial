# 打包上线

## 修改环境

- 切换到master主干

```bash
git checkout master
git merge develop
```

- 修改api.js

## 编辑构建脚本

- 创建pro/index.html
- 创建build.js

```js
// build.js
var jtaroBundle = require('jtaro-bundle')
var uglify = require('rollup-plugin-uglify')

jtaroBundle.bundle({
  rollupPlugins: [uglify()],
  origin: 'dev/index.html',  // 站点目录
  target: 'pro/index.html',  // 源目录
  copies: ['./assets/', './data/'],  // 目标文件
  sourceMap: true
})
```

- 配置package.json的npm运行脚本命令

```json
"scripts": {
  "dev": "cd dev && node jtaro-module/server.js",
  "pro": "cd pro && node ../dev/jtaro-module/server.js",
  "build": "node build.js"
}
```

## 打包运行

```bash
npm run build
npm run pro
```

测试没问题后将代码放到服务器上运行，收工。
