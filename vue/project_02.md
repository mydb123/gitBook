---
title: 项目(2)
---

## 获取列表数据
<img :src="$withBase('/front/vue/获取数据.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 添加索引
<img :src="$withBase('/front/vue/索引.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 状态开关
<img :src="$withBase('/front/vue/状态开关.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

### Vue中插槽-----特殊特性slot、slot-scope与指令v-slot的使用方法
1. `slot`、`slot-scope`已经被废弃推荐使用vue2.6.0中的**v-slot**；但是这边还是对新旧方法对做一下使用说明。
2. 具名插槽：给slot起个名字
`slot-scope使用：`
```js
<body>
   <div id="app">
      <Test>
         <div slot="default" slot-scope="gain">//作用域插槽的用法（slot-scope）
            {{ gain.msg }}
         </div>
         
      </Test>
   </div>

   <template id="test">
      <div>
         <slot name="default" :msg="msg"> </slot>
         <p>这里是test组件</p>
      </div>
   </template>
</body>
```
```js
<script>
   new Vue({
      el:"#app",
      components:{
         'Test':{
            template:"#test",
            data(){
               return {
                  msg:"你好"
               }
            },
         }
      }
   })
</script>
```
`作用域插槽：v-slot的用法`
```js
<body>
   
   <div id="app">
      <Test>
         <template v-slot:header="gain">//v-slot定义作用域插槽
            <div>
                  <h3>slot</h3>
                  <p> {{gain.msg}} </p>
            </div>
         </template>
           
      </Test>
   </div>
   
   <template id="test">
      <div>
         <slot name="header":msg="msg"></slot>
         <p>这里是test组件</p>
      </div>
   </template>
   
</body>
<script>
   Vue.component('Test',{
      template:"#test",
      data(){
         return {
            msg:'这里是头部'
         }
      }
   });

   new Vue({

   }).$mount("#app")
</script>

```
**Vue2.6.0中使用v-slot指令取代了特殊特性slot与slot-scope，但是从上述案例可以看出，v-slot在使用时，需要在template标签内，这点大家要注意**

## 分页效果
<img :src="$withBase('/front/vue/页码.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 状态按钮改变发送请求
<img :src="$withBase('/front/vue/按钮状态.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 弹出框
<img :src="$withBase('/front/vue/弹出层.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 重置表单
<img :src="$withBase('/front/vue/重置表单.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 获取数据get
1. 当使用`get`请求的时候请求必须是以`params`传参
<img :src="$withBase('/front/vue/get传参.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 安装element-ui没有的组件
1. 在安装依赖中可以找
2. 在从main.js中可以导入与注册
3. 使用的时候查询api
