---
title: 常用特性
---

## 表单操作

+ .number:转化为数值
```js
    <input v-model.number="age">
```
+ .trim: 去除开头和结尾的空格
```js
    <input v-model.trim="age">
```
+ .lazy: 将input切换为change事件
```js
    //失去焦点触发
    <input v-model.change="age">
```

## 自定义指令
```js
    //定义在man.js
    //关键字**Vue.directive**  **inserted**
    Vue.directive('focus',{
        inserted: function(el){
            //el标识指令绑定元素
            //focus()表示自动定义到文本框是一个jsapi方法
            el.focus();
        }
    })
    <div v-focus></div>
```
## 自定义指定携带参数
```js
    var msg = 111
 Vue.directive('color',{
        inserted: function(el,binding){
          console.lof(binding.value)
          //111
        }
    })
    <div v-color="msg"></div>

```
## 局部自定义指令
意思就是在一个文件中使用的指令
```js
//这里的directive与methods平级
directives:{
    focus:{
       inserted:function(el){
           el.focus
       }
    }
    <div v-focus></div>

}
```

## 计算属性  computed
**计算属性与方法的区别:计算属性是基于依赖进行缓存的，而方法不缓存**
```js
data:{
    msg:"hello"
}
computed:{
    kk(){
        先 .split('')分割在.reverse()反转在join('')拼接到一起
        return this.msg.split('').reverse().join('')
    }
}
<div>{{kk}}<div>
```

###  侦听器   watch
- 验证用户是否可用的地方用到失去焦点的时候
- 使用watch来响应数据的变化
- 一般用于异步或者开销较大的操作
- watch 中的属性 一定是data 中 已经存在的数据 
- **当需要监听一个对象的改变时，普通的watch方法无法监听到对象内部属性的改变，只有data中的数据才能够监听到变化，此时就需要deep属性对对象进行深度监听**

```html
 <div id="app">
        <div>
            <span>名：</span>
            <span>
        <input type="text" v-model='firstName'>
      </span>
        </div>
        <div>
            <span>姓：</span>
            <span>
        <input type="text" v-model='lastName'>
      </span>
        </div>
        <div>{{fullName}}</div>
    </div>

  <script type="text/javascript">
        /*
              侦听器
            */
        var vm = new Vue({
            el: '#app',
            data: {
                firstName: 'Jim',
                lastName: 'Green',
                // fullName: 'Jim Green'
            },
             //watch  属性 定义 和 data 已经 methods 平级 
            watch: {
                //   注意：  这里firstName  对应着data 中的 firstName 
                //   当 firstName 值 改变的时候  会自动触发 watch
                firstName: function(val) {
                    this.fullName = val + ' ' + this.lastName;
                },
                //   注意：  这里 lastName 对应着data 中的 lastName 
                lastName: function(val) {
                    this.fullName = this.firstName + ' ' + val;
                }
            }
        });
    </script>
```

## 过滤器 fileter

```js
//定义在main.js
Vue.fileter('format',function(value,arg){
    //过滤的业务逻辑
    /** 
 * 对日期进行格式化， 
 * @param date 要格式化的日期 
 * @param format 进行格式化的模式字符串
 *     支持的模式字母有： 
 *     y:年, 
 *     M:年中的月份(1-12), 
 *     d:月份中的天(1-31), 
 *     h:小时(0-23), 
 *     m:分(0-59), 
 *     s:秒(0-59), 
 *     S:毫秒(0-999),
 *     q:季度(1-4)
 * @return String
 * @author yanis.wang
 * @see http://yaniswang.com/frontend/2013/02/16/dateformat-performance/
 */
function dateFormat(date, format) {
    if (typeof date === "string") {
        var mts = date.match(/(\/Date\((\d+)\)\/)/);
        if (mts && mts.length >= 3) {
            date = parseInt(mts[2]);
        }
    }
    date = new Date(date);
    if (!date || date.toUTCString() == "Invalid Date") {
        return "";
    }
    var map = {
        "M": date.getMonth() + 1, //月份 
        "d": date.getDate(), //日 
        "h": date.getHours(), //小时 
        "m": date.getMinutes(), //分 
        "s": date.getSeconds(), //秒 
        "q": Math.floor((date.getMonth() + 3) / 3), //季度 
        "S": date.getMilliseconds() //毫秒 
    };

    format = format.replace(/([yMdhmsqS])+/g, function(all, t) {
        var v = map[t];
        if (v !== undefined) {
            if (all.length > 1) {
                v = '0' + v;
                v = v.substr(v.length - 2);
            }
            return v;
        } else if (t === 'y') {
            return (date.getFullYear() + '').substr(4 - all.length);
        }
        return all;
    });
    return dateFormat(value,age);
}
    renturn date()
})

{{kk|format('yyyy-MM-dd')}}

```
## 生命周期 8个
| 生命周期函数 | 阶段 |
| ------ | ------------------------------------------------------------ |
| beforeCreate  | 在实例初始化之后，数据观测和事件配置之前被调用 此时data 和 methods 以及页面的DOM结构都没有初始化   什么都做不了 |
| created       | 在实例创建完成后被立即调用此时data 和 methods已经可以使用  但是页面还没有渲染出来 |
| beforeMount   | 在挂载开始之前被调用   此时页面上还看不到真实数据 只是一个模板页面而已 |
| mounted       | el被新创建的vm.$el替换，并挂载到实例上去之后调用该钩子。  数据已经真实渲染到页面上  在这个钩子函数里面我们可以使用一些第三方的插件 |
| beforeUpdate  | 数据更新时调用，发生在虚拟DOM打补丁之前。   页面上数据还是旧的 |
| updated       | 由于数据更改导致的虚拟DOM重新渲染和打补丁，在这之后会调用该钩子。 页面上数据已经替换成最新的 |
| beforeDestroy | 实例销毁之前调用                                             |
| destroyed     | 实例销毁后调用 |

## 数组变异方法
- 在 Vue 中，直接修改对象属性的值无法触发响应式。当你直接修改了对象属性的值，你会发现，只有数据改了，但是页面内容并没有改变
- 变异数组方法即保持数组方法原有功能不变的前提下对其进行功能拓展

| 方法 | 解释 |
| ------ | ------------------------------------------------------------ |
| `push()`    | 往数组最后面添加一个元素，成功返回当前数组的长度             |
| `pop()`     | 删除数组的最后一个元素，成功返回删除元素的值                 |
| `shift()`   | 删除数组的第一个元素，成功返回删除元素的值                   |
| `unshift()` | 往数组最前面添加一个元素，成功返回当前数组的长度             |
| `splice()`  | 有三个参数，第一个是想要删除的元素的下标（必选），第二个是想要删除的个数（必选），第三个是删除 后想要在原位置替换的值 |
| `sort()`    | sort()  使数组按照字符编码默认从小到大排序,成功返回排序后的数组 |
| `reverse()` | reverse()  将数组倒序，成功返回倒序后的数组                  |

## 替换数组
- 不会改变原始数组，但总是返回一个新数组

| 方法 | 解释 |
| ------ | ------------------------------------------------------------ |
| `filter` | `filter()` 方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素。 |
| `concat` | `concat()` 方法用于连接两个或多个数组。该方法不会改变现有的数组 |
| `slice`  | `slice()` 方法可从已有的数组中返回选定的元素。该方法并不会修改数组，而是返回一个子数组 |