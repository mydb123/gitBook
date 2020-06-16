---
title: app遇到的问题
---
## 时间格式化

1. 先在js文件定义时间格式
```js
function happenTimeFun(num){
	let date = new Date(num);
	let y = date.getFullYear();
	let MM = date.getMonth() + 1;
	MM = MM < 10 ? ('0' + MM) : MM;//月补0
	let d = date.getDate();
	d = d < 10 ? ('0' + d) : d;//天补0
	let h = date.getHours();
	h = h < 10 ? ('0' + h) : h;//小时补0
	let m = date.getMinutes();
	m = m < 10 ? ('0' + m) : m;//分钟补0
	let s = date.getSeconds();
	s = s < 10 ? ('0' + s) : s;//秒补0
	return y + '-' + MM + '-' + d + ' ' + h + ':' + m+ ':' + s;
}
```
2. 在需要的页面引入刚刚定义的格式
<img :src="$withBase('/tools/application/引入.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")


3. 格式数据的代码内容
<img :src="$withBase('/tools/application/代码内容.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")



