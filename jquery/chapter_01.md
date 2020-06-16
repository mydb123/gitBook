---
title: jQuery
---
jQuery就是一个封装了很多方法的库
**引入jquery.js**
## jquery的入口函数
1. 
```js
    $(document).ready(function(){
        alert("hello")
    })
```
2. 推荐写法 
```js
     $(function(){
        alert("hello")
    });

```

## jq的each方法

1. 利用jq的each静态方法遍历数组
    + 第一个参数: 当前遍历到的索引
    + 第二个参数: 遍历到的元素
注意:jq的each可以遍历伪数组
```js
    var arr = [1,2,3,4,5]
$.each(arr,function(index,value){
    console.log(index,value)
})
```