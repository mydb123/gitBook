---
title: JSX语法
---
## jsx语法
> 什么是JSX语法：就是符合 xml 规范的 JS 语法；（语法格式相对来说，要比HTML严谨很多）
1. **如何启用 jsx 语法？**
   + 安装 `babel` 插件(安装包就是为了少写代码)

     - 运行`cnpm i babel-core babel-loader babel-plugin-transform-runtime -D`
     - 运行`cnpm i babel-preset-env babel-preset-stage-0 -D`

   + 安装能够识别转换jsx语法的包 `babel-preset-react` 
     + 运行`cnpm i babel-preset-react -D`

   + 在新项目中创建 `.babelrc` 配置文件

     ```json
     {
       "presets": ["env", "stage-0", "react"],
       "plugins": ["transform-runtime"]
     }
     ```

   + 添加babel-loader配置项：

     ```js
     //webpack.confing.js的module.exports中
     module: { //要打包的第三方模块
         rules: [
           { test: /\.js|jsx$/, use: 'babel-loader', exclude: /node_modules/ }//exclude里面的是排除项,仔细看一下
         ]
     }
     ```
3. **在 jsx 中混合写入 js 表达式**：在 jsx 语法中，要把 JS代码写到 `{ }` 中
    **其中的key需要加,加给最外面的元素** 
   + 渲染数字
    ```js
     //index.js
     //导入包
     import React from 'react' //创建组件,虚拟DOM元素

     import ReactDOM from 'react-dom'  // 把创建好的组件和虚拟dom放在页面上展示的

     let a = 10

     //调用渲染render
     ReactDOM.render(<div>{a}</div>, document.getElementById('app'))
    ```
   + 渲染字符串
    ```js
     let string = '你好,世界'

     ReactDOM.render(<div>{string}</div>, document.getElementById('app'))
    ```
   + 渲染布尔值
    ```js
     let Boolean = true

     ReactDOM.render(<div>{Boolean ? "真的":"假的"}</div>, document.getElementById('app'))
    ```
   + 为属性绑定值
    ```js
     let title = '999'
        //什么情况下需要使用{}呢? 当我们需要在jsx控制区域内,写js表达式了,则需要把js代码写到{}中
     ReactDOM.render(<div><p title:{title} >这个是一个p标签</p></div>, document.getElementById('app'))
    ```
   + 渲染jsx元素
    ```js
     let h1 = <h1>阿斯顿法国红酒看来</h1>

     ReactDOM.render(<div>{h1}</div>, document.getElementById('app'))
    ```
   + 渲染jsx元素数组
   ```js
     let arr = [
         <h1>这是h1</h1>
         <h2>这是h2</h2>
     ]

     ReactDOM.render(<div>{arr}</div>, document.getElementById('app'))
    ```
   + 将普通字符串数组，转为jsx数组并渲染到页面上【两种方案】**(.forEach,.map)**
    ```js
     let arrstr = ["费兰克","乔巴","路飞","索隆","香克斯","艾斯","娜美","布鲁克"]
     const  namearr = []
     arrstr.forEach(item=>{
        const  temp=  <h5 key="item.index" >{item}</h5>
        namearr.push(temp)
     })
        // const a = arrstr.map(item=>{
        //     reten  <h3 key="item.index">item</h3>
        // }) 
        //ReactDOM.render(<div>{a}</div>, document.getElementById('app'))
     ReactDOM.render(<div>{namearr}</div>, document.getElementById('app'))
    ```
## 注意
1. jsx中注释怎么写
 在React中注释`{/*什么什么内容*/}`
```js 
{
  //这是注释
}
```
2. **为 jsx 中的元素添加class类名**：需要使用`className` 来替代 `class`；`htmlFor`替换label的`for`属性

