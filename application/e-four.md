---
title: 全局配置和组件
---

## globalStyle全局配置外观
```js
// 在pages文件下
"globalStyle": {
		"navigationBarTextStyle": "white",//导航栏标题颜色 
		"navigationBarTitleText": "卓源智能",//标题
		"navigationBarBackgroundColor": "#0faeff",//导航栏背景颜色
		"backgroundColor": "#F8F8F8" //下拉显示出来的窗口的背景色
	}
```
## text
* `selectable`; //文本是否可选
* `space`; //ensp,emsp,nbsp

## view
* `hover-class`; (指定按下去的样式类。当 hover-class="none" 时，没有点击态效果)
* `hover-stop-propagation`;(false;指定是否阻止本节点的祖先节点出现点击态)
* `hover-start-time`;(50;按住后多久出现点击态，单位毫秒)
* `hover-stay-time`;(400;手指松开后点击态保留时间，单位毫秒)

## button
* `size`;(default;按钮的大小)
* `type`;(default;按钮的样式类型)
* `disabled`;(false;是否禁用)
* `loading`;(false;名称前是否带 loading 图标)

## image
* `src`;(图片资源地址)
* `mode`;(图片裁剪、缩放的模式)
* `lazy-load`;(false;图片懒加载。只针对page与scroll-view下的image有效)
* `fade-show`;(true;图片显示动画效果)

### uni-app的生命周期
1. `onLaunch` (当uni-app 初始化完成时触发（全局只触发一次）)
2. `onShow` (当 uni-app 启动，或从后台进入前台显示)
3. `onHide` (当 uni-app 从前台进入后台)

## 下拉刷新
1. 需要在 pages.json 里，找到的当前页面的pages节点，并在 style 选项中开启 enablePullDownRefresh,刷新功能  

2. ```js
	onPullDownRefresh(){
		setTime(()=>{
			//这里写需要加载的数据
			nui.stopPUllDowRefresh()
		},1000)
	}
	```