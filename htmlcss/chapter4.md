---
title: H5
---
## H5语义化标签
<img :src="$withBase('/front/htmlcss/H5语义化.png')">

+ `<header></header> 页眉:`主要用于页面的头部的信息介绍，也可用于板块头部；  

+ `<nav></nav> 导航：`包含链接的一个列表；  

+ `<section> <section> 页面上的版块：`用于划分页面上的不同区域,或者划分文章里不同的节；

+ `<aside></ aside>侧边栏:` 素标签可以包含与当前页面或主要内容相关的引用、侧边栏、广告

+ `<time></time>日期；`用来表现时间或日期；

+ `<footer></footer>页脚：`页面的底部或者版块底部。

+ `<video></video>视频：`播放视频的标签

+ `<audio></audio>: `音频标签

## cs3的结构伪类选择器
+ `ul li:first-chid `选择ul里面第一个孩子第一个的`li`  

+ `ul li:last-chid`选择ul里面最后一个孩子的`li`

+ `ul li:nth-chid(n)`**这里的n可是数字也可以是3倍的`n`** 

注意:`section div:last-chid(n)`和`section div:nth-of-type(n)`区别
1. 第一个是想去看`:last-chid(n)`指定的元素再去看`div`
2. 第二个是先去找子元素中是否有这个div在去找`nth-of-type(n)`(建议使用这个)

## 伪选择器
```css
    /*前面*/
    .nav::before{
        content: "";
        display: block;
        z-index:999;
    };
    .nav::after;/*后面*/
```
## css不撑大盒子
+ `box-sizing:border-box`给父元素添加  

+ `filter:blur(5px)`图像模糊使用

## css新增过度
+ `transition: width .5s, height .5s;`属性过度

+ `transition:all 0.2s`属性过度

+ `transform: translate(-50%,-50%);`配合着定位让盒子居中

+ `transform:rotate(360deg)`旋转角度 

+ `animation:`动画里面有很多自己查

