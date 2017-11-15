# vue-resume

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report

# run unit tests
npm run unit

# run all tests
npm test
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

## 主目录结构

```
.
├── README.md
├── build                    # build 目录用于存放构建脚本，比如 webpack 配置文件
├── config                  # config 目录用于存放一些配置信息，比如配置打包后的 bundle 文件存放在哪里
├── index.html           # 首页
├── node_modules
├── package.json
├── src                       # 除了首页，其他的源代码都在 src 目录里
├── static                   # static 目录用于放置静态资源，比如 favicon.ico 文件等
└── test                     # 单元测试等代码放在 test 目录里

```


## src目录结构
```
src
├── App.vue              # App.vue 是主组件，后面讲什么是组件
├── assets                 # assets 用于放置代码之外的资源，比如图片、字体等
├── components       # components 用于放置主组件之外的组件，vue 组件的后缀都是 .vue
├── main.js                # JS 入口文件，浏览器执行的第一行代码在这里，所以我们先看这里
└── router                 # 路由，目前用不到

```
