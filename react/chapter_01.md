---
title: react初始化
---

## 创建基本的webpack4.x项目
1. 运行`npm init -y`快速初始化项目
2. 在项目根目录创建src源代码和dist产品目录
3. 在src目录下创建`index.html`
4. 使用cnpm 安装webpack,运行`cnpm i webpack -D`
    + 全局运行 `npm i cnpm -g`
5. 注意:webpack4.x提供了约定大于配置的概念:目的是为了减少配置文件的体积
    + 默认约定:
    + 打包的入口是`src`=>`index.js`( 这离的index.js也就是main)
    + 4.x中新增mode选项(为必选项),可选的值为development和production
    + 下面内容是创建的webpack.config.js(自己创建)文件中的
```js
// 向外暴露文件,需要遵从webpack的语法 
module.default = {
    mode:"development"//development(开发模式打包文件不会压缩) production(发布模式文件会压缩)
    // 在 webpack 4.x中,最大的特征 ,就是约定大于配置 约定,默认的打包入口文件的路径是src->index.js
    plugins:[   //这端代码的具体看下面打包
        htmlplugin
    ]
}    
    
```
## 事实打包编译文件配置
1. `cnpm i webpack-dev-sever -D`(安装包)
```js
"scripts":{
    "dev":"webpack-dev-server  --open(自动打开浏览器) --port 3000(改变端口号)"
}
```
2. `cnpm i html-webpack-plugin -D`
```js
    //此内容在webpack.config.js创建
    const path = require("path") 
    const HtmlWebpackPlugin= requeire('html-webpack-plugin') //导出在内存中自动生成 index页面的创建
    //创建插件的实例对象
    const HtmlPulgin = new HtmlWebpackPlugin({
        tmeplate : path.join(__dirname,'./src/index.html'),//源文件(path.jsin意思是拼接路径的; __dirname当前的那层目录)
        filename:'index.html',//生成内存中首页的名称
    })
```

