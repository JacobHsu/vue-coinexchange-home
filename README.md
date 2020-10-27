# BIZZAN_web_front

[CoinExchange](https://gitee.com/cexchange/CoinExchange) Web_Front
http://118.25.133.182/  
[huobi](https://www.huobi.com/zh-cn/exchange/)

## charting_library

pages\exchange\Exchange.vue

```js
getKline() {
      ...
        library_path:
          process.env.NODE_ENV === "production"
            ? "/assets/charting_library/"
            : "/src/assets/js/charting_library/",
```

## Install Prerequisites
The following dependencies are required to run an instance:

1. NodeJS - 9.11.2
2. Npm - 5.6.0

## Build Setup

``` bash
# install dependencies
npm i

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

```

## Build Fixed

`npm install --save sockjs-client@1.1.4`
`npm install --save compression-webpack-plugin@1.1.11`

src\main.js

```js
const router = new VueRouter({
    mode: 'hash', // 'history',
    routes
});
```

build\webpack.base.conf.js

```js

module.exports = {
    context: path.resolve(__dirname, '../'),
    entry: {
        app: ['./src/main.js'] // ['./node_modules/babel-polyfill/dist/polyfill.js','./src/main.js']
    },
    ...
    ,
    externals: {
        'vue': 'Vue',
        'vue-router': 'VueRouter',
        'jquery': 'jQuery',
        "moment": "moment"
    },
```

index.html

```html
    <script src="https://cdn.bootcss.com/babel-polyfill/6.26.0/polyfill.min.js"></script>
    <script src="https://cdn.bootcss.com/vue/2.5.3/vue.min.js"></script>
    <script src="https://cdn.bootcss.com/vue-router/3.0.1/vue-router.min.js"></script>
    <script type="text/javascript" src="http://unpkg.com/iview/dist/iview.min.js"></script>
    <script src="https://cdn.staticfile.org/jquery/1.11.2/jquery.min.js"></script>
    <script src="https://cdn.bootcss.com/moment.js/2.22.1/moment.min.js"></script>
```


## Future
1. 统一改用less,实验可以通过变量覆盖的方式定制主题;
2. iview组件按需引用;
3. exchange.vue等大文件，代码拆分/组件化;


## 前端开发规范
1. 页面使用驼峰法命名，如Exchange.vue,WithdrawRecord.vue,名称为英文单词，并且要能正确描述该模块功能
2. 变量命名禁止使用拼音，特别是拼音缩写
3. 页面比较多时应该使用文件夹做分类
4. 模块中data变量应该尽量少，比较多时应该使用子对象进行管理


