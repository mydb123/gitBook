---
title: React案例
---
```js
//1. 导包
import react from 'react'
import ReactDOM from 'react-dom'

//使用functinon函数定义普通的无组件函数
function CmtItem(props){
    renturn
    //组件内部的key不需要了
    <div key={props.id}>
        <h1>评论人:{props.user}</h1>
        <p>评论内容:{props.content}</p>
    </div>
}


//定义父组件使用class关键字定义组件

class Cmtlist extends React.component{
    constructor(){
        super()
        this.state = {
            CommentList:[
                {id:1 user:"路飞", content:'哈哈,沙发'}
                {id:2, user:"索大", content:'哈哈,沙发'}
                {id:3,user:"香克斯", content:'哈哈,沙发'}
                {id:4, user:"弗兰克", content:'哈哈,沙发'}
                {id:5, user:"乔巴", content:'哈哈,沙发'} 
            ]
        }
    }
    render(){
        return 
        <div>
        <h1>这是评论列表组件</h1>
        {this.state.CommentList.map(item =>
        // <div key={item.id}>
        // <h1>评论人:{item.user}</h1>
        // <p>评论内容:{item.content}</p>
        // </div>
        //简写:
        <CmtItem {...item} key={item.id}></CmtItem>
        )}
        </div>
    }
}


//调用渲染
ReactDOM.render(
    <div>
    <Cmtlist></Cmtlist>
    </div>,document.getELementBYID('app'))
```

## 文件的抽离
```js
//1. 导包
import react from 'react'
function CmtItem(props){
    renturn
    <div >
        <h1>评论人:{props.user}</h1>
        <p>评论内容:{props.content}</p>
    </div>
}

export {CmtItem} 




// 其他文件需要用需要导入
import CmtItem from '上面代码文件的路径'
```
****************************************
```js
import react from 'react'
//定义父组件使用class关键字定义组件
import CmtItem from '上面代码文件的路径'

class Cmtlist extends React.component{
    constructor(){
        super()
        this.state = {
            CommentList:[
                {id:1 user:"路飞", content:'哈哈,沙发'}
                {id:2, user:"索大", content:'哈哈,沙发'}
                {id:3,user:"香克斯", content:'哈哈,沙发'}
                {id:4, user:"弗兰克", content:'哈哈,沙发'}
                {id:5, user:"乔巴", content:'哈哈,沙发'} 
            ]
        }
    }
    render(){
        return 
        <div>
        <h1>这是评论列表组件</h1>
        {this.state.CommentList.map(item =>
        // <div key={item.id}>
        // <h1>评论人:{item.user}</h1>
        // <p>评论内容:{item.content}</p>
        // </div>
        //简写:
        <CmtItem {...item} key={item.id}></CmtItem>
        )}
        </div>
    }
}

export  {Cmtlist}




import Cmtlist from '上面代码文件的路径'

```

## class样式问题
{/* 注意: 在jsx中如果想写行内样式了,不能魏style设置字符串的值*/}
{/* 而是写成 style= { {clor:"red" } }*/}
{/* 在行内样式中如果数值类型的可以不使用引号,是字符串类型的必须得用引号包裹*/}
```js
//抽离
const aaa= { color:'red',fosize:'36px' }
<h1 style={aaa}>哈哈哈

<div style={aaa.bbb}></div>
</h1>

```

 + 第二次封装
 const aaa = {
     bbb:{color:'red',fosize:'36px'},
     ccc:{color:'red',fosize:'36px'}
 }
 + 第三次封装
 ```js
 //创建一个js文件放代码
 export default {
      bbb:{color:'red',fosize:'36px'},
     ccc:{color:'red',fosize:'36px'}

 }
 其他地方要用直接导入
 import style from "上面代码的路径"
 ```

## class美化组件
1. 新键文件cmtlist.css文件
```css
    .div{
        color:pink;
    }
```
2. 导入列表需要的样式表  
`import cssobj form 'cmtlist.css文件'`

3. 因为文件不识别的问题我们需要装一下 `cnpm i style-loader css-loader -D`在这里配置我们需要得去webpack.confing.js配置文件中的mode配置一下

4. 使用css `<div className='类名'></div>`

## css文件样式冲突问题
 在文件`webpack.confing.js`配置文件中的`mode`部分
 ```js
    mode:{ //所有第三方 模块的配置规则
    rules:{ //第三方配置规则
      {test:/\.css$/,use:['style-loader','css-loader?modules']} //添加modules参数
    }
    }
```  

使用css `<div className='cssobj.title'></div>`

注意: **css 模块化 只针对类选择器和id选择器  像什么标签div什么的都不支持**

## 怎么安装自己定义字体的loader
 在文件`webpack.confing.js`配置文件中的`mode`部分
 ```js
    mode:{ //所有第三方 模块的配置规则
    rules:{ //第三方配置规则
      {test:/\.ttf|woff|woff2$/,use:'url-loader']} //打包处理字体的loader
    }
    }
    cnpm i url-loader -D
    cnpm i file-loader -D
```  