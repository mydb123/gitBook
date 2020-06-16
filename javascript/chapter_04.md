---
title: 作用域/对象/数组/字符串
---
## 全局作用域/局部作用域
```js
    var num = 30; //这个是全局作用域
    function fn(){
        //这里是局部作用域
        var num = 10;
    }
```
## 作用域链
<img :src="$withBase('/front/javascript/作用域链.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 函数预解析
<img :src="$withBase('/front/javascript/预解析.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## 创建对象
1. `var obj = {};`创建了一个空对象
    + 里面的属性或者方法我们采用键值对的形式**键 属性名 : 值 属性值**(这里就叫做键值对)
    + 多个属性由`,`隔开
    + `sayhi: dunction(){console.log("hi")}`(写在对象里面)方法`:`后面跟着是一个匿名函数
2. `var obj = new Object()`;创建一个空对象
    + ```js
        //我们用等号 = 的赋值方法 添加1对象的属性和方法 每个属性之间用 ; 分号结束
        obj.name="路飞";
        obj.age = 18;
      ```
3. 构造函数创建对象
<img :src="$withBase('/front/javascript/构造函数创建对象.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## Math对象
+ `Math.abs(1);`1, 取绝对值  

+ `Math.floor(1.6);`1 向下取整  

+ `Math.ceil(1.1);`2 向上取整  

+ `Math.round(1.6);`2 四舍五入取整  

+ `Math.random`
<img :src="$withBase('/front/javascript/Math.random.jpg')">

## Date对象
```js
    var date = new Date();//Date是一个日期对象 必须使用new来调用创建日期对象
```
|      方法名            |           说明                   |          代码                  |
|------------------------|----------------------------------|--------------------------------|
|      getFullYear()     |          获取当年                |       dateObj.getFullYear()    |
|      getMonth()        |          获取当月                |       dateObj.getMonth()       |
|      getDate()         |          获取当天                |       dateObj.getDate()        |
|      getDay()          |          获取星期几(周日到周六)  |       dateObj.getDay()         |
|      getHours()        |          获取当前小时            |       dateObj.getHours()       |
|      getMinutes()      |          获取当前分钟            |       dateObj.getMinutes()     |
|      getSeconds()      |          获取当前秒数            |       dateObj.getSeconds()     |

## Array对象
```js
    var fruits = ['Apple', 'Banana'];
    var arr = new Array(); //创建了一个空数组
    var arr2 = new Array(2);//这个2表示数组长度为2 里面有两个空的数组元素
    var arr3 = new Array(2,3); //等价于[2,3] 这样里面就有2个数组2和3
```
1.  通过索引访问数组元素**.length**
```js
    var first = fruits[0];
    // Apple

    var last = fruits[fruits.length - 1];
    // Banana
```
2. 遍历数组**forEach**
```js
    fruits.forEach(function (item, index, array) {
        console.log(item, index);
    });
    // Apple 0
    // Banana 1
```

3. 添加元素到数组的末尾**push()**
```js
    var newLength = fruits.push('Orange');
    // newLength:3; fruits: ["Apple", "Banana", "Orange"]
```
4. 删除数组末尾的元素**pop()**
```js
    var last = fruits.pop(); // remove Orange (from the end)
    // last: "Orange"; fruits: ["Apple", "Banana"];
```
5. 添加元素到数组的头部**unshift()**
```js
    var newLength = fruits.unshift('Strawberry') // add to the front
    // ["Strawberry", "Banana"];
```
6. 删除数组最前面（头部）的元素**shift()**
```js
    var first = fruits.shift(); // remove Apple from the front
    // first: "Apple"; fruits: ["Banana"];
```
7. 找出某个元素在数组中的索引**indexOf()**
```js
    fruits.push('Mango');
    // ["Strawberry", "Banana", "Mango"]

    var pos = fruits.indexOf('Banana');
    // 1
```
8. 通过索引删除某个元素**splice()**
```js
    var removedItem = fruits.splice(pos, 1); // this is how to remove an item

    // ["Strawberry", "Mango"]
```
9. 数组的分割`join()`,`tostring()`
<img :src="$withBase('/front/javascript/数组的风割方法.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

## String操作方法
1. concat/substr
<img :src="$withBase('/front/javascript/字符串方法1.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

2. replace/split
<img :src="$withBase('/front/javascript/字符串方法2.jpg')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

