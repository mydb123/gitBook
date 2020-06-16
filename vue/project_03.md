---
title: 项目(3)
---
## tabs标签页
+ 在element-ui中看他具体用法
<img :src="$withBase('/front/vue/tabs页签.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 清空input触发的事件
<img :src="$withBase('/front/vue/清空数据.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 根据id删除商品
<img :src="$withBase('/front/vue/删除商品.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

 ## 通过编程式导航跳转页面
<img :src="$withBase('/front/vue/编程时跳转.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## router-link的用法
1. `<router-link :to="{path:'/test',query: {name: id}}">`跳转`</router-link>`(id是参数)使用：this.$route.query.id  

2. `<router-link :to="'/test/'+id">`跳转`</router-link>`(id是参数)  

注意：router-link中链接如果是‘/’开始就是从根路由开始，如果开始不带‘/’，则从当前路由开始

## 字符串和数值的相互转换
+ 字符串转换成数值直接`-0`就可以了  

+ 数值转换为字符串直接`+''`就可以了

## 上传文件添加请求头
<img :src="$withBase('/front/vue/上传文件添加请求头.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 向数组中push对象
<img :src="$withBase('/front/vue/push对象.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 将数组转换为字符串
+ 调用数组的方法
```js
//将数组的每一项以','的方式分割
this.addFrom.join(',')
```
