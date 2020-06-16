---
title: React绑定和生命周期
---
## React中绑定事件 
1. 事件名称都是React的提供的,因此名称的首写字母必须大写`onClick`,`onMouseOver`
2.  <img :src="$withBase('/front/react/button绑定事件.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

3. 
    > 注意: 在React中如果想为了state中的数据重新赋值,请不要 this.state.*** = 值
    > 应该 调用React提供的this.setState({msg:'123'})


<img :src="$withBase('/front/react/React传参.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## setState两个注意点
<img :src="$withBase('/front/react/setState.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## input数据框绑定事件
1. 可以给input 输入框提供一个readOnly这样页面就没有报错
2. 还可以给input 提供一个`onChange={ (e)=>this.texChanged(e)} ref='txt'` 
<img :src="$withBase('/front/react/input事件绑定.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")
