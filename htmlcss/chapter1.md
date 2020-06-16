---
title: flex布局
---
## 简介
Flex 是 Flexible Box 的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。  
任何一个容器都可以指定为 Flex 布局。

## flex使用
1. 必须给父级元素添加**display: flex;**

## 父元素的属性
* flex-direction
* flex-wrap
* flex-flow
* justify-content
* align-items
* align-content

## flex-direction属性
```js
.box {
  flex-direction: row | row-reverse | column | column-reverse;
}
```
[图片](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071005.png)
1. row（默认值）：起点在左端, 从左到右
2. row-reverse：起点在右端, 从右到左
3. column：起点在上端,从上到下
4. olumn-reverse：起点在下,从下到上

## flex-wrap属性
```js
.box{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```
1. nowrap（默认）：不换行。
2. wrap：换行,第一行在最上方,
3. wrap-reverse：换行，第一行在下方。

## justify-content属性
```js
.box {
  justify-content: flex-start | flex-end | center | space-between | space-around;
}
```
1. flex-start（默认值）：左对齐
2. flex-end：右对齐
3. center： 居中
4. space-between：两端对齐，项目之间的间隔都相等(开头和结尾无空格)。
5. space-around：每个项目两侧的间隔相等,(开头和结尾有空格)。