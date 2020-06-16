---
title: 自定义tarBar
---
## 自定义tarbar使用步骤
1. 创建自定义文件
```js
<!--
    @时间：2020-03-16
    @描述：自定义底部导航栏
    @使用：
        在main.js全部引入：
            import tabBar from "@/pages/common/tabBar.vue"
            Vue.component('tabBar', tabBar)
        
        在需要显示的页面底部添加：
        <view>
            上面是内容块
　　　　　　　// 其中uni-p-b-98是公共样式类名，表示padding-bottom: 98upx;  设置的98upx是和底部导航栏的高度保持一致，页面的内容就不会被底部导航遮挡住啦
            <view class="uni-p-b-98"></view>
　　　　　　　// 最后引入自定义组件，并传当前栏目对应的pagePath到自定义组件，显示当前栏目的选中样式
            <tabBar :pagePath="'/pages/tabBar/home/home'"></tabBar>
        </view>
 -->
<template>
    <view class="uni-tabbar">
        <view class="uni-tabbar__item" v-for="(item,index) in tabbar" :key="index" @tap="changeTab(item)">
            <!-- <view class="icon" :class="[item.fontIcon , item.pagePath == pagePath?'uni-active':'']"></view> -->
            <!-- 上面使用的是字体图标，解决切换页面的时候图标会闪的效果，毕竟每切换一个页面都会闪一下不太好看，可以切换使用下面的图片方式 -->
            <view v-if="true" class="uni-tabbar__bd">
                <view class="uni-tabbar__icon">
                    <image v-if="item.pagePath == pagePath" class="uni-w-42 uni-h-42 taber1" mode="aspectFit" :src="item.selectedIconPath"></image>
                    <image v-else class="uni-w-42 uni-h-42 taber1" mode="aspectFit" :src="item.iconPath"></image>
                </view>
            </view>
            <view class="uni-tabbar__label" :class="{'active': item.pagePath == pagePath}">
                {{item.text}}
            </view>
        </view>
    </view> 
</template>

<script>
    export default {
        props: {
            pagePath: null
        },
        data() {
            return {
                page: 'contact',
                showPage: false,
                containerHeight: 400,
                tabbar: [
                    {
                        "pagePath": "/pages/home",
                        "iconPath": "../static/font/zhuye_gray.png",
                        "selectedIconPath": "../static/font/zhuye_selected.png",
                        "text": "首页", 
                        "fontIcon": "icon-shouye"
                    },
　　　　　　　　　　　　// 这里是要动态切换的栏目，先隐藏，动态追加
                    // {
                    //     "pagePath": "/pages/tabBar/manage/manage",
                    //     "iconPath": "/static/tabBar/home.png",
                    //     "selectedIconPath": "/static/tabBar/home_col.png",
                    //     "text": "管理",
                    //     "fontIcon": "icon-guanli"
                    // },
                    {
                        "pagePath": "/pages/myinfo",
                        "iconPath": "../static/font/mine_gray.png",
                        "selectedIconPath": "../static/font/mine_selected.png",
                        "text": "我的",
                        "fontIcon": "icon-wode"
                    }
                ]
            };
        },
        mounted() {
            // true为判断条件，根据实际的需求替换即可
            if(false) {
                this.tabbar.splice(1,0,
                    {
                        "pagePath": "/pages/sys2/index",
                        "iconPath": "/static/tabBar/home.png",
                        "selectedIconPath": "/static/tabBar/home_col.png",
                        "text": "系统2",
                        "fontIcon": "icon-guanli"
                    }
                )
            }
        },
        methods: {
            changeTab(item) {
                this.page = item.pagePath;
　　　　　　　　　　// 这里使用reLaunch关闭所有的页面，打开新的栏目页面
                uni.reLaunch({
                    url: this.page
                });
            },
        }
    }
</script>

<style lang="scss" scoped>

    [nvue] uni-scroll-view, [nvue] uni-swiper-item, [nvue] uni-view {
        flex-direction: unset;
    }
    [nvue-dir-column] uni-swiper-item, [nvue-dir-column] uni-view {
        flex-direction: unset;
    }
    .uni-tabbar {
        position: fixed;
        bottom: 0;
        z-index: 999;
        width: 100%;
        display: flex;
        justify-content: space-around;
        height: 98upx;
        padding: 16upx 0;
        box-sizing: border-box;
        border-top: solid 1upx #ccc;
        background-color: #fff;
        box-shadow: 0px 0px 17upx 1upx rgba(206, 206, 206, 0.32);
        .uni-tabbar__item {
            display: block;
            line-height: 24upx;
            font-size: 20upx;
            text-align: center;
			.taber1{
				width: 40rpx;
				height: 40rpx;
			}
        }
        .uni-tabbar__icon {
            height: 42upx;
            line-height: 42upx;
            text-align: center;
        }
        .icon {
            display: inline-block;
        }
        .uni-tabbar__label {
            line-height: 24upx;
            font-size: 24upx;
            color: #999;
            &.active {
                color: #143071;
            }
        }
		
    }
</style>
```
2. 从main.js引入处
<img :src="$withBase('/tools/application/引入tabar.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")


3. 在页面需要用这个标签
<img :src="$withBase('/tools/application/页面.png')">
![](https://github.com/mydb123/gitBook/blob/master/photo/git/生成密钥.jpg "图片")


