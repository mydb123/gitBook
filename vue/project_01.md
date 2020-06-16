---
title: 项目
---

## 起始
1. 打开`cmd` 输入`Vue ui`
2. 一步一步后到功能面板
3. 需要的`bable`, `Route`r,使用配置文件
4. 配置: 第一个关上 第二个选`Standard config `
5. 插件->添加插件->`vue-cli-plugin-element`安装 
6. 依赖->安装依赖-axios

## 登录退出
1. 登录状态保持

如果服务器和客户端同源，建议可以使用`cookie`或者`session`来保持登录状态

如果客户端和服务器跨域了，建议使用`token`进行维持登录状态。

2. 登录逻辑：

在登录页面输入账号和密码进行登录，将数据发送给服务器

服务器返回登录的结果，登录成功则返回数据中带有`token`

客户端得到`token`并进行保存，后续的请求都需要将此`token`发送给服务器，服务器会验证`token`以保证用户身份。

+ 打开App.vue(根组件)，将根组件的内容进行操作梳理(template中留下根节点，script中留下默认导出，去掉组件，style中去掉所有样式)
```js
  <template>
    <div id="app">
      <router-view></router-view>
    </div>
  </template>

  <script>
  export default {
    name: 'app'
  }
  </script>

  <style>
  </style>
```
## 创建文件重定向
<img :src="$withBase('/front/vue/login.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

+ 安装依赖`less`或者是`scss`
+ 定义全局样式
<img :src="$withBase('/front/vue/全局样式.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

+ 为`input`框绑定`v-model`双项绑定
```js
<script>
export default {
  data() {
    return {
      //数据绑定
      loginForm: {
        username: 'admin',
        password: '123456'
      },
    }
  },

}
</script>
```
<img :src="$withBase('/front/vue/input的双向绑定.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")


## 添加表单验证的步骤

1. 给`<el-form></el-form>`添加属性 **:rules="rules"**，rules是一堆验证规则，定义在script、中

2. 
```js
在script中添加rules：export default{ data(){return{......, rules: {

          name: [
            { required: true, message: '请输入活动名称', trigger: 'blur' },
            { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
          ],
          region: [
            { required: true, message: '请选择活动区域', trigger: 'change' }
          ]

}......
```
## 验证规则
3. 通过`<el-form-item>`的prop属性设置验证规则`<el-form-item label="活动名称" prop="name">`
<img :src="$withBase('/front/vue/表单校验(1).jpg')">
<img :src="$withBase('/front/vue/表单校验(2).jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")


## 表单的预校验
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

<img :src="$withBase('/front/vue/确定的时候校验(1).jpg')">

<img :src="$withBase('/front/vue/确定的时候校验(2).jpg')">

## 使用axios挂在到原型
<img :src="$withBase('/front/vue/axios的使用.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 请求
<img :src="$withBase('/front/vue/发送请求.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 将登陆token储存到sessionStorage里
<img :src="$withBase('/front/vue/储存token.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 配置路由导航守卫
<img :src="$withBase('/front/vue/路由导航守卫.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 实现退出功能
```js
export default {
    methods:{
        logout(){
            window.sessionStorage.clear();
            this.$router.push('/login');
        }
    }
}
```
## (优化)element-ui按需导入方法(我是直接全部导入的)
```js
import Vue from 'vue'
import { Button, Form, FormItem, Input, Message } from 'element-ui'

Vue.use(Button)
Vue.use(Form)
Vue.use(FormItem)
Vue.use(Input)
// 进行全局挂载：
Vue.prototype.$message = Message
```
## 请求拦截器
<img :src="$withBase('/front/vue/请求拦截器.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 路由重定向
+ 这里需要在页面上写上路由占位符`<router-view></router-view>`
<img :src="$withBase('/front/vue/路由重定向.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")


