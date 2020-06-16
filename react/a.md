---
title: 首页
---

## React介绍
* React起源于Facebook的内部项目,因为该公司对市场所有的JavaScript MVC 框架,都不满意,就决定自己写一套,用来假设Instagram(照片交友)的网站,做出来以后,发现这套东西很好用,就再2013年5月开源了
* 由于  React 的设计思想极其独特,属于革命性创新,性能出众,代码逻辑却非常简单,所以,越来越多的人开始关注和使用,认为它可能是将来开发的主流工具
* 清楚两个概念:  
    -  **library(库)** 小而巧的库,方便从一个库切换到另外的库;但是代码几乎不会改变
    -  **Framework(框架)** 大而全的是框架,提供了一整套的的解决方案;所以项目中间想切换到另一个框架比较困难

## React与vue的对比
1. **什么是模块化：**是从**代码**的角度来进行分析的；把一些可复用的代码，抽离为单个的模块；便于项目的维护和开发；
2. **什么是组件化：** 是从 **UI 界面**的角度 来进行分析的；把一些可服用的UI元素，抽离为单独的组件；便于项目的维护和开发；
3. **组件化的好处:** 随着项目规模的增大，手里的组件越来越多；很方便就能把现有的组件，拼接为一个完整的页面；
4. **Vue是如何实现组件化的：** 通过 `.vue` 文件，来创建对应的组件；
   + template  结构
   + script        行为
   + style           样式

## React中几个核心的概念
### 虚拟DOM (Virtual Document Object Model)
+ **DOM的本质是什么**: 浏览器中的概念,用js对象来表示页面上的元素,并提供了操作Dom对象的API
+ **什么是React中的虚拟DOM**:是框架中的概念,是程序员用js对象来模拟页面上的DOM和DOM的嵌套;
+ **为什么要实现虚拟DOM:** 为了实现页面中, DOM元素的高效更新


## Diff算法
+ tree Diff:(新旧两个DOM树,逐层对比的过程,就是tree Diff; 当整颗DOM逐层对比完毕,则所需要的被按需要更新的元素,必然能够找到)
+ componter Diff:(在进行tree Diff的时候,每一层中,组件级别的对比,叫做componter Diff
    - 如果对比前后,组件的类型相同,则**暂时**认为此组件不需要被更新;
    - 如果对比前后,组件类型不同,则需要移除旧组件,创建新组建,并追加到页面上;)
+ element Diff:(在进行对比的时候,如果两个组件类型相同,则需要进行元素急别的对比,这叫做element Diff)
<img :src="$withBase('/front/react/Diff.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

<img :src="$withBase('/front/react/虚拟DOM的概念.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")
