---
title: 获取元素
---
## 根据id获取
+ 使用`getElementById()`方法可以获取带ID的元素对象
```js
    <div id="item"></div>
    <script>
    var timer = documet.getElementById('time')
    </script>
```
## 通过HTML5新增的方法获取
1.` document.getElementsByClassName('类名')`;//根据类名返回元素对象集合
```js
    <div class="box">123</div>
    <div class="box">456</div>
    <script>
    var boxs = documet.getElementsByClassName('box')
    </script>
```
2. `documet.querySelector`;//返回指定选择器第一个元素对象
```js
    <div class="box">123</div>
    <div class="box">456</div>
    <script>
    var firxBox = documet.querySelector('.box')
    </script>
```
2. `documet.querySelectorAll`;//返回指定选择器所有元素对象集合
```js
    //可以选出全部的box
    <div class="box">123</div>
    <div class="box">456</div>
    <script>
    var firxBox = documet.querySelectorAll('.box')
    </script>
```
## 获取特殊元素 (body,html)
1. 获取body `document.body`  

2. 获取html `document.documentElement`

## 执行事件及其事件列表
```js
    <div>123</div>
    <script>
        const div= document.querySelector("div")
        div.onclick = function (){
            consloe.log('我被选中了')
        }
    </script>
```
| 鼠标事件  | 触发条件 |
| ------------- | ------------------------------------------------------------ |
| onclick       | 鼠标点击触发      |
| onmouseover   |  鼠标经过触发     |
| onmouseout    | 鼠标离开触发      |
| onfocus       | 获取鼠标焦点触发  |
| onblur        | 失去鼠标焦点触发  |
| onmousemove   | 鼠标移动触发      |
| onmouseup     | 鼠标谈起触发      |
| onmousedown   | 鼠标按下触发      |