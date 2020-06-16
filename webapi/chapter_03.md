---
title: Es6
---
## var ,let ,const的区别
1. 使用`var`声明的变量,其作用域为**该语句所在的函数内,且存在变量提升现像**
2. 使用`let`声明的变量,其作用域为**该语句所在的代码块内,不存在变量提升**
3. 使用`const`声明的常量,在后面出现的**代码中不能修该**

## 对象结构赋值
**对象结构允许我们使用变量的名字匹配对象的属性 匹配成功 将对象属性的值赋值给变量**
```js
    let person = {name:'lisi',age:30,sex:'男'};
    //let {name,age,sex} = person;
    // 在结构语法中左边的name只作用于属性匹配,右边的才是真正的变量
    let {name:myName} = person
    console.log(myName);//lisi
```

## 箭头函数
```js
    ()=>{}
    //在箭头函数中 如果函数中只有一句代码
    // 并且代码的执行结果就是函数的返回值 函数体大括号可以省略
    const sum = (n1,n2)=>{
        n1+n2;
    }
    //const sum = (n1,n2)=>n1+n2
    // const result = sum(10,20);
    // consloe.log(result);//30
```
```js
    var obj = {  //对象不能产生作用域
        age = 20
        say:()=>{
            alert(this.age);
        }
    }
    obj.say();//undefined
```

## 剩余参数
```js
    const sum = (...args)+>{
        let total = 0;
        args.forEach(item=>{
            total += item
        })
    }
    console.log(sum(10,20));//30
```
```js
    let ary = ["张三","李四","王五"]
    let [s1,s2]= ary
```

## 扩展运算符
```js
    let ary = [1,2,3];
    console.log(...ary)
```
```js
    // 合并数组
    let ary1 = ["1","2","3"]
    let ary2 = ["4","5","6"]
    let ary3 = [...ary1,...ary2];
    console.log(ary3)
    ary1.push(...ary2)
```

## 构造函数方法 Array.from()
将伪数组转换为真正的数组
```js
    let array = {
        "0":"张三",
        "1":"李四"
    }
    var ary = Array.from(array,(item)=>{
        return item * 2
    });
    console.log(ary);//数组
```

## Find()/Findindex()  
**Find()找出第一个符合条件的数组成员,如果没找到就返回undefined**
**Findindex()找出第一个符合条件的数组成员的位置,如果没有就返回-1**
```js
    var ary = [
        {
            id:1,
            name:"李一"
        },
        {
            id:2,
            name:"张三"
        }
    ]
   var add = ary.find((item,index)=>{
        return item.id ==2
    })
    console.log(add);// {id:2, name:"张三"}
```

## 模板字符串
```js
    let result = {
        name = "张三",
        age = 24
    }
    cosnt fn = ()=>{
        return "我是fn函数"
    }
    let html = `
        <div>
            <span>${result.name}</span>
            <span>${result.age}</span>
            <span>${fn()}</span>
        </div>
    `
```

