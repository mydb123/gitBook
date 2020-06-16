---
title: css样式
---
## 基础选择器
1. id选择器
```css
#box{
    width:100px;
}
<div id="box"></div>
```

## 后代选择器(重)
```html
     ul li{
        width:100px;
    }
    <ul>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
        <li></li>
    </ul>
```
## 子选择器(重)
```html
    <!--选择最近的一个儿子 -->
    .nav>a{
        width:100px;
    }
    <div class="nav">
        <a href="#">我是儿子</a>
        <p>
            <a href="#">我是孙子</a>
        </p>
    </div>
```
## 并集选择器(重)
```css
    div,p{
        width:100px;
    }
```
## 伪类选择器
+ a:link (选择访问的链接)   

+ a:visited (选择被访问的链接)

+ a:hover (鼠标移动上去的链接)

+ a:active(鼠标按下去未放的链接)

## 图片复合型写法
```css
    div{
        /* 红色/绿色/蓝色/透明度 */
        background: rgba(0,0,0,0.3);
        background: 背景颜色 背景图片地址 背景平铺 背景图像滚动 背景图片位置;
    }
```

## css属性
+ `text-decoration`给文本添加属性
    > none(默认值什么都没)
    > underline(下划线)

+ `text-indent:10px`首航缩进


### 选择器优先级
| 选择器    | 选择器权重             |
| ----------- | ------------------ |
| 继承或者*     | 0,0,0,0      |
| 元素选择器   | 0,0,0,1     |
| 类选择器,伪类选择器 | 0,0,1,0           |
| id选择器  | 0,1,0,0 |
|  行内样式或style    | 1,0,0,0 |
| !iimportant | 最高级      |


## 浮动float:left;
1. 给父级添加`overflow:hidden`清楚浮动
2. 给父元素添加`.clearfix:after`
```css
    .clearfix::after{
        content: "";
        display: block;
        height: 0;
        clear: both;
        visibility: hidden;
    }
```

## 定位(自绝父相)
```css
    position:relative /*相对定位给父亲加*/
    position:absolute /*绝对定位给儿子加*/
    position：fixed /*固定定位*/ 
```

## 元素的显示和隐藏
```css
    display:none;/*隐藏*/
    display:block;/*显示*/
```
```css
    visibility: hidden; /*隐藏*/
    visibility: visible; /*显示*/
```
```css
    overflow: hidden; /*溢出隐藏*/
    overflow: scroll; /*溢出部分显示滚动条，不溢出也显示*/
    overflow: auto; /*溢出部分显示滚动条*/
```
```css
    white-space:nowrap;/* 强制一行显示*/
    text-overflow:ellipsis; /*文字用省略号替代超出部分*/
```
## 精灵图的使用
```
    background: url("")no-repeat -182px 0 ;
```
##  vertical-align使用方式
+  `vertical-align: bottom|middle|top;`(图片和文字对齐方式)
+ 给图片添加`vertical-align: bottom|middle|top;`使图片下面的白线消失

