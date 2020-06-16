---
title: 变量
---
浏览器本身不会执行js代码,而是通过内置的js引擎来执行js代码,**js引擎执行代码时会逐行解释每一行代码**

## 获取数据类型(typeof)
```js
var number = 10
consloe.log(typeof number)
```


## 转换为字符串
+ toString();  `num.toString()`  

+ string()强制转换;  `string(num)`

+ 加号拼接字符串; `num+''`  


## 转化为数字类型
+ parselnt();`parselnt("12")`  

+ parseFloat()有小数点;`parseFloat("12")`

+ Number()强制转换;`Number("12")`

+ js隐式转换;`"12"-0`

## 转换为布尔型
+ Boolean()  

 `"",0,NaN,null,undefined` **这些都会被转化为`false`其余全部转换为`true`**