---
title: 起始
---


## 双向数据绑定
- 当数据发生变化的时候，视图也就发生变化
- 当视图发生变化的时候，数据也会跟着同步变化
- **v-model**是一个指令，限制在 `<input>、<select>、<textarea>、components`中使用

## mvvm

- MVC 是后端的分层开发概念； MVVM是前端视图层的概念，主要关注于 视图层分离，也就是说：MVVM把前端的视图层，分为了 三部分 Model, View , VM ViewModel
- m   model    
  - 数据层   Vue  中 数据层 都放在 data 里面
- v   view     视图     
  - Vue  中  view      即 我们的HTML页面    
- vm   （view-model）     控制器     将数据和视图层建立联系        
  - vm 即  Vue 的实例  就是 vm    

## 事件修饰符 /案件修饰符 //自定义按键修饰符
1. .stop组织冒泡
```js
    //这里可以防止父元素被点击
<a @click.stop="function" >按钮</a>
```

2. .prevent阻止默认行为
```js
    //这里我们组织默认行为可以防止a标签跳转到百度去
<a @click.prevent="function" >百度</a>
```

3. .keyup.enter 回车键
```js
    //使用这个是优化用户操作,用户可以按回车键提交登陆
<input @keyup.enter="function">
```
4. .delete 删除键
```js
    // 按键盘的delete就可以全部删除input框文中的内容
<input @click.delete="function">
```
5. 全局config.keyCodes对象
```js
    //kk是自定定义的名字 112是每一个按键的都有他自己的id
    Vue.config.keyCodes.kk=112
    <input @keyup.112="function">
```

## v-model的底层原理
+ 使用v-bind:简写:和v-on简写@来实现的
```js
    <input @click=kk($event)>
    
        //这里可以用event.target.value获取到input框中的内容
    kk(event){
        console.log(event.target.value)
    }
```  

## clss样式动态处理
+ 对象语法
```html
<ul class="box" :class="{textColor:isColor, textSize:isSize}">
    <li>学习Vue</li>
    <li>学习Node</li>
    <li>学习React</li>
</ul>
  <div :style="{color:activeColor,fontSize:activeSize}">对象语法</div>

<sript>
var vm= new Vue({
    el:'.box',
    data:{
        isColor:true,
        isSize:true，
    	activeColor:"red",
        activeSize:"25px",
    }
})
</sript>
<style>

    .box{
        border:1px dashed #f0f;
    }
    .textColor{
        color:#f00;
        background-color:#eef;
    }
    .textSize{
        font-size:30px;
        font-weight:bold;
    }
</style>
```

## v-if/v-for/v-show循环
```js
<div v-if="条件"></div>
<div v-else-if="条件"></div>
<div v-else></div>
<div v-show="条件"></div>
```

```js
<div v-for="(item,index) in list" :key="item.id" ></div>
```