<template>
	<view class="uni-tabbar">
		<view class="uni-tabbar__item" v-for="(item,index) in tabbar" :key="index" @click="changeTab(item)">
			<view class="uni-tabbar__bd">
				<view class="uni-tabbar__icon">
					<image v-if="item.pagePath == pagePath" class="icon-img" mode="aspectFit"
						:src="item.selectedIconPath"></image>
					<image v-else class="icon-img" mode="aspectFit" :src="item.iconPath"></image>
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
			pagePath: {
				type: String,
				// default: "/pages/index/index"
			}
		},
		data() {
			return {
				page: '/pages/index/index',
				tabbar: [{
						"text": "首页",
						"pagePath": "/pages/index/index",
						"selectedIconPath": "/static/tab/home_selected.png",
						"iconPath": "/static/tab/home.png"
					},
					{
						"text": "发现",
						"pagePath": "/pages/discover/index",
						"selectedIconPath": "/static/tab/discover_selected.png",
						"iconPath": "/static/tab/discover.png"
					},
					{
						"text": "消息",
						"pagePath": "/pages/message/index",
						"selectedIconPath": "/static/tab/message_selected.png",
						"iconPath": "/static/tab/message.png"
					},
					{
						"text": "我的",
						"pagePath": "/pages/PersonCore/index",
						"selectedIconPath": "/static/tab/mine_selected.png",
						"iconPath": "/static/tab/mine.png"
					}
				]
			};
		},
		watch: {
			pagePath: {
				handler(val) {
					console.log('pagePath监听===val', val)
				},
				immediate: true
			}
		},
		mounted() {
			// 根据自己的业务需求判断条件为true，替换即可
			// if (true) {
			// 	this.tabbar.splice(0, 0, {
			// 				"text": "首页",
			// 				"pagePath": "pages/index/index",
			// 				"selectedIconPath": "./static/tab/home-active.png",
			// 				"iconPath": "static/tab/home.png"
			// 			},
			// 			{
			// 				"text": "发现",
			// 				"pagePath": "pages/discover/discover",
			// 				"selectedIconPath": "static/tab/cart-active.png",
			// 				"iconPath": "static/tab/cart.png"
			// 			},
			// 			{
			// 				"text": "消息",
			// 				"pagePath": "pages/message/message",
			// 				"selectedIconPath": "static/tab/search-active.png",
			// 				"iconPath": "static/tab/search.png"
			// 			},
			// 			{
			// 				"text": "我的",
			// 				"pagePath": "pages/PersonCore/person-core",
			// 				"selectedIconPath": "static/tab/my-active.png",
			// 				"iconPath": "static/tab/my.png"
			// 			})
			// }
		},
		methods: {
			changeTab(item) {
				console.log('item',item)
				this.page = item.pagePath;
				// 使用reLaunch关闭所有的页面，打开新的栏目页面
				// uni.redirectTo({
				//     url: this.page,
				// 	success:()=>{
				// 		console.log('定向成功')
				// 	},
				// 	fail:()=>{
				// 		console.log('定向失败')
				// 	}
				// });
				// uni.switchTab({
				//     url: this.page,
				// 	success:()=>{
				// 		console.log('tab切换成功')
				// 	},
				// 	fail:()=>{
				// 		console.log('tab切换失败')
				// 	}
				// })
				uni.reLaunch({
					url: this.page,
					success: () => {
						console.log('tab切换成功')
					},
					fail: () => {
						console.log('tab切换失败')
					}
				});

				console.log(this.page)
			},
		}
	}
</script>

<style lang="scss" scoped>
	.uni-tabbar {
		position: fixed;
		bottom: 0;
		left: 0;
		z-index: 999;
		width: 100%;
		display: flex;
		justify-content: space-around;
		height: 98upx;
		box-sizing: border-box;
		border-top: solid 1upx #ccc;
		background-color: #fff;
		box-shadow: 0px 0px 17upx 1upx rgba(206, 206, 206, 0.32);

		.uni-tabbar__item {
			display: block;
			line-height: 24upx;
			font-size: 20upx;
			text-align: center;
			width: 25%;
		}

		.uni-tabbar__icon {
			height: 24px;
			line-height: 24px;
			text-align: center;
		}

		.icon {
			display: inline-block;
		}

		.uni-tabbar__label {
			line-height: 24upx;
			font-size: 24upx;
			color: #999;
			padding: 3px 0;

			&.active {
				color: #1ca6ec;
			}
		}

		.icon-img {
			height: 24px;
			width: 24px;
		}
	}
</style>
