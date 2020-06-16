---
title: class关键字
---

### 最基础的组件基本结构
```js
  //如果需要使用class定义组件，必须让自己的组件，继承来自React.Component
  class 组件名称 extends React.Component{
      //在组件内部必须要有render()函数
    render(){
      //render函数中必须返回合法的jsx虚拟的DOM结构
      return <div>这是class基本组件</div>
    }
  }
```
```js
  import React from 'react'
  class Movie extends React.Component{
    render(){
      return <div>这是class基本组件</div>
    }
  }
  ReactDOM.render(<Movie></MOvie> document.getElementById('app'))
```

## 第二种创建组件的方式
> class关键字创建组件   
> ES6中class关键字,是实现面向对象编程的新形式
1. 创建一个动物类
```js
  class Animal(){
    //这是类中的 构造函数
    //每一个类中,都有一个构造器,如果我们程序员没有手动定义构造器,那么,可以认为内部有一个隐形的,看不见的空构造器
    //类似于constructor(){}
    //构造器的作用,就是每当new这个类的时候,必须优先执行,构造器中的代码
    constructor(name,age){
      this.a = name;
      this.b = age
    }
  }
  const p1= new Animal('大黄',11)
  //console.log(p1.a) //实例属性
  //console.log(p1.a) //实例属性

```
2. [静态属性]:通过构造函数,直接访问的属性,叫做静态属性
    
  ```md
    在class内部,通过static 修饰的属性, 就是静态属性,在于**constructor**平级
    **static** info = "eee"
    console.log(Animal.info) //info是Animal的静态属性
  ```

## class子类继承父类
```js
    //这是父类[这里可以把这个父类比成原型对象上prototype]

    class Person(){
         constructor(a,b){
            this.name = a
            this.age = b
        }
    }

    //这里是美国人
    //在 class 类中,可以使用extends 关键字,实现子类继承父类
    //语法 class子类extends父类{}
    class American extends person{

        // constructor(a,b){
        //     this.name = a
        //     this.age = b
        // }

    }
    const a1 = new American('jack',20)
    console.log(a1)
    
    //这里是中国人
    class Chinese(){

        // constructor(a,b){
        //     this.name = a
        //     this.age = b
        // }
    }
    const a2 = new Chinese('张三',18)
    console.log(a2)
```
## super的使用
1. 为什么要在constructor 中调用 super
    ```md
      因为,如果一个子类,通过`extends` 关键字继承了父类,那么在子类的`constructor`构造函数中,必须优先调用 `super()`
    ```
2. super 是什么
    ```md
    super是一个函数,而且他是父类的构造器,子类中的`super`,其实就是父类中这个`constructor`构造器的一个引用
    ```
3. 为什么调用`super()`之后,a1实例的name和age 都变成了underfined了
    ```md
    传的时候将new一直传给子类的`constructor`在从`constructor`传给`super`
    ```

## class语法规范
```js

 class Chinese extends person{

        constructor(a,b,c){
          //语法规范： 在子类中this只能在super()的后面使用
          super()
            this.name = a
            this.age = b
            this.idnumber =c
        }
    }
    const a2 = new Chinese('张三',18,'13956650000')
    console.log(a2)
```

## props传参
```js
class  Movie extends React.component{
  //render函数的作用是渲染当前组件对应的虚拟dom元素
  render(){
    //在class关键字创建的组件中，如果想使用外界传过来的props参数，直接通过this.props.***可以直接访问
    return<div>这里是movie组件-----{this.props.name}</div>
  }
}
cosnt user = {
  age:"ls",
  name:15,
  zender:"55"
}
React.reder(<Movie name={user.name} age={user.age}></Movie>,document.getElementByID('app'))
```

## 两种创建组件方式的对比
<img :src="$withBase('/front/react/组件对比.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

 
> 注意: 使用class关键字创建的组件,有自己的私有数据(this.state)和生命周期函数;  
> 注意: 但是使用function创建的组件只有props没有自己的私有数据和生命周期函数
1. 用(左边)**构造函数**创建出来的组件叫做:"无状态组件"
2. 用(右边)**lass关键字**创建出来的组件叫做:"有状态组件"

<img :src="$withBase('/front/react/例1.png')">  
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

***********************************************
***********************************************
***********************************************
***********************************************
<img :src="$withBase('/front/react/例1.1.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")

