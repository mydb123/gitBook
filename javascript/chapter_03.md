---
title: 数组/函数
---
## 创建数组
+ **var 数组名 = new Array()** //创建了一个arr空数组
+ **var arr = []**;

## 数组的遍历for/forEach()/map()
1. for
<img :src="$withBase('/front/javascript/数组的遍历.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

2. forEach（）遍历对象类型数组
```js
// arr.forEach( function(item){
//             console.log(item)
//         } )
const arr = [
    {id:1,name:'zhangsan'},
    {id:2,name:'lisi'},
    {id:3,name:'wangwu'}
]

arr.forEach( function(item){
            console.log(item.id + '---' +  item.name)
})
// 输出结果：
// 1-----zhangsan
// 2-----lisi
// 3-----wangwu
```
2. map()方法
```js
var newArr = arr.map( function(value,index){
    console.log(value + '---' + index)    
    return value + 10		
    })		
    console.log(newArr)

```
## 新增数组元素
```js
    var arr =  ["aaa","bbb","ccc"];
    arr[3] = "ddd";
    // 这样可以追加数组
```

## 函数
声明函数
```js
    function kkk(){
        conslole.log("hi~~")
    }
    kkk()
```

## 函数传参
```js
    function kk(num1,num2){
        consloe.log(num1+num2)
    }
    kk(1,2)
```
## 函数返回值return
<img :src="$withBase('/front/javascript/函数返回值.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")


