---
title: 页面之间的传值
---
### uni-app页面之间的传值
1. 传值之前的需要传值内容(godevicefull(item))
```js
<view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in listData" :key="item.id" @click="godevicefull(item)" >
```
2. 可以先创建对象这样可以对象的形式传过去
<img :src="$withBase('/tools/application/传值1.png')">

3. 页码传值的话还可以用拼接的方法来传值 代码:
```js
url: './detail/loginfoDetail?id='+e.id+'&module='+e.module
```
4. 下个页面如何接受传过来的值
```js
<script>
	export default {
		data() {
			return {
				deviceDetail:{}
			};
		},
		onLoad(option) {
			console.log(option)//这个就是传过来的这个值
			this.deviceDetail= JSON.parse(option.deviceDetail);
		}
	}
</script>
```
5. 传值与接受值的时候需要转换
**JSON.stringify()** 方法用于将 **JavaScript** 值转换为 **JSON** 字符串。
```js
godevicefull(e) {
    let detail = {
        id: e.id,//编号
        alarmType: e.alarmType,//报警类型
        alarmLevel: e.alarmLevel,//报警等级
    };
    uni.navigateTo({
        url: 'devicefull?deviceDetail=' + JSON.stringify(detail)//这里需要转换成json模式才能传值
        // url: './detail/loginfoDetail?id='+e.id+'&module='+e.module+'
    });
},
```
6. 接受值的适合需要转换
我们可以使用 **JSON.parse()** 方法将数据转换为 **JavaScript** 对象。
```js
onLoad(option) {
    this.deviceDetail= JSON.parse(option.deviceDetail);//这里接受时需要转换成js对象模式才能使用
}
```
### uni-app的get和post方法封装
```js
export function post(url,data = {}){
    return uni.request({
		sslVerify:false,
		url:url,
		data:data,
		header: {
			'content-type':'application/x-www-form-urlencoded;charset = utf-8' 
		},
		method:'POST'
	})
}

export function get(url,data = {}){
    return uni.request({
		url:url,
		data:data,
	}) 
}
```