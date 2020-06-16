---
title: 组件创建和传值
---
> **使用构造函数来创建组件**，如果要接收外界传递的数据，需要在 构造函数的参数列表中使用`props`来接收；
>
> 必须要向外return一个合法的JSX创建的虚拟DOM；

+ 创建组件：

  ```jsx
  function Hello () { 
  	// return null 
  	return <div>Hello 组件</div>
  }
  ```

+ 为组件传递数据：

  ```jsx
  const dog = [name:"",name:"",name:""]
  // 使用组件并 为组件传递 props 数据
    // ReactDOM.render渲染
  //<Hello name={dog.name} age={dog.age} gender={dog.gender}></Hello>
  <Hello {...dog}></Hello>

  // 在构造函数中，使用 props 形参，接收外界 传递过来的数据
  function Hello(props) {    //这里的HELLO就是等会<hello></hello>
    // props.name = 'zs'
    console.log(props)
    // 结论：不论是 Vue 还是 React，组件中的 props 永远都是只读的；不能被重新赋值；

    return <div>这是 Hello 组件 --- {props.name} --- {props.age} --- {props.gender}</div>
  }
  ```
## es6...的新特性
```js
var a = {
    name:"张三",
    age:3,
    gender:"男"
};
    
var b = {
    adder:"暗室逢灯",
    ...a
}
console.log(b)

```
1. 父组件向子组件传递数据

2. 使用{...obj}属性扩散传递数据

3. 将组件封装到单独的文件中

4. 注意：组件的名称首字母必须是大写  ​

## 组件放置于单独文件
1. 在src文件下创建一个组件components`Hello.jsx` (*想让jsx文件正常解析的话确保webpack.config.js中有jsx这一项*) 
     + 创建好了之后要在文件内部暴露出去`export default Hell` 这文件夹中必须导入React
     + 文件需要导入`import Hell from 路径` 这里必须加后缀名
<img :src="$withBase('/front/react/公用模块.png')">
2. 在文件webpack.confing.js配置文件中和mode,module平级的地方加上
    ```js
        resolve:{
            extensions:['.js','jsx','json'] //表示这个几个文件的后缀名不需要写了,忽略不写
            alias:{
                '@':path.join(__dirname,'../src')//这样,@符号就表示项目中src的这一层路径
            }
        }
    ```

    ```js
    mode:{ //所有第三方 模块的配置规则
    rules:{ //第三方配置规则
      {test:/\.js|jsx$, use:'babel-loader',exclude:/node_modules//} //这里千万得记住添加exclude排除项
      {test:/\.css$/,use:['style-loader','css-loader']} //打包处理css样式第三方loader
    }
    }
    ```
### @符号的解释
注意: **项目路径中的@符号主要是表示根目录的src这一层目录**

