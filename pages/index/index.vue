<template>
	<view>
		<view class="uni-p-b-98">这里是内容块</view>
		<tabBar :pagePath="'/pages/index/index'"></tabBar>
	</view>

</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		// onLoad(options) {
		// 	console.log('页面加载了', options)
		// },
		// onShow() {
		// 	console.log('页面显示了')
		// },
		// onReady() {
		// 	console.log('页面初次渲染了')
		// },
		// onHide() {
		// 	console.log('页面隐藏了')
		// },
		// onUnload() {
		// 	console.log('页面卸载了')
		// },
		// onPullDownRefresh() {
		// 	console.log('下拉刷新')
		// 	setTimeout(() => {
		// 		uni.stopPullDownRefresh();
		// 	}, 2000)
		// },
		// onReachBottom() {
		// 	console.log('页面触底了')
		// },
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
