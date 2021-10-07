<template>
	<view>

		<view class="content">
			<view class="wrap">
				<u-swiper :list="list"></u-swiper>
			</view>
			<view class="wrap_bottom">
				<div class="wrap_bottom_items">
					<span>
						<image src="../../static/home/profit.png" mode="aspectFit" style="height: 50rpx;width: 50rpx;">
						</image>
					</span>
					<span>可观收益</span>
				</div>
				<div class="wrap_bottom_items">
					<span>
						<image src="../../static/home/quick.png" mode="aspectFit" style="height: 50rpx;width: 50rpx;">
						</image>
					</span>
					<span>方便快捷</span>
				</div>
				<div class="wrap_bottom_items">
					<span>
						<image src="../../static/home/time.png" mode="aspectFit" style="height: 50rpx;width: 50rpx;">
						</image>
					</span>
					<span>省时省力</span>
				</div>
			</view>
		</view>
		<view class="myCar">
			<div>我的车辆</div>
			<div @click="goList">
				<span style="font-size: 24rpx;">全部车辆</span>
				<span>
					<image src="../static/mine/next.png" mode="aspectFit" style="width: 24rpx;height: 24rpx;vertical-align: middle;padding-left: 10rpx;"></image>
				</span>
			</div>
		</view>
		<u-swipe-action :show="item.show" :index="index" v-for="(item, index) in carlist" :key="item.id" @click="click"
			@open="open" :options="options">
			<view class="item u-border-bottom">
				<image mode="aspectFill" :src="item.images" />
				<!-- 此层wrap在此为必写的，否则可能会出现标题定位错误 -->
				<view class="title-wrap">
					<text class="title u-line-2">{{ item.title }}</text>
					<text class="title u-line-2 item_content ">{{ item.content }}</text>
					<span
						style="color: #fff;font-size: 20rpx;background:#F99159;margin-top: 10rpx;padding: 0 5px;">{{ item.footer }}</span>
				</view>
			</view>
		</u-swipe-action>
		<view class="content">
			<div class="wrap_bottom_Btn" @click="markInfo">
				立即上传车辆
			</div>
			<view class="home_title">
				<div class="home_tltle_header">摩托圈自我介绍</div>
				<div>你也可以和朋友这样介绍我</div>
				<div class="home_intro">
					<table style="width: 100%;">
						<tbody>
							<tr>
								<th rowspan="2">
									<image src="../../static/home/fun.png" mode="aspectFit"
										style="width: 50rpx;height: 50rpx;">
									</image>
								</th>
								<th class="txt_left">有趣</th>
								<th rowspan="2">
									<image src="../../static/home/convenient.png" mode="aspectFit"
										style="width: 50rpx;height: 50rpx;"></image>
								</th>
								<th class="txt_left">方便</th>
							</tr>
							<tr>
								<th class="txt_txt">你想要的车我们都有</th>
								<th class="txt_txt">简单易懂人性化定制</th>
							</tr>
							<tr>
								<th rowspan="2">
									<image src="../../static/home/Efficient.png" mode="aspectFit"
										style="width: 50rpx;height: 50rpx;"></image>
								</th>
								<th class="txt_left">高效</th>
								<th rowspan="2">
									<image src="../../static/home/flexible.png" mode="aspectFit"
										style="width: 50rpx;height: 50rpx;"></image>
								</th>
								<th class="txt_left">灵活</th>
							</tr>
							<tr>
								<th class="txt_txt">实时沟通及时有效</th>
								<th class="txt_txt">随时随地便捷畅通</th>
							</tr>
						</tbody>
					</table>

				</div>
			</view>
			<tabBar :pagePath="'/pages/index/index'"></tabBar>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
						image: 'https://cdn.uviewui.com/uview/swiper/1.jpg',
						title: '昨夜星辰昨夜风，画楼西畔桂堂东'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/2.jpg',
						title: '身无彩凤双飞翼，心有灵犀一点通'
					},
					{
						image: 'https://cdn.uviewui.com/uview/swiper/3.jpg',
						title: '谁念西风独自凉，萧萧黄叶闭疏窗，沉思往事立残阳'
					}
				],
				carlist: [{
						id: 1,
						title: '本田 CM3000',
						content: '沪A·83294',
						footer: '待审核',
						images: 'https://cdn.uviewui.com/uview/common/logo.png',
						show: false
					},
					{
						id: 2,
						title: '本田 CM3000',
						content: '沪A·83294',
						footer: '审核失败',
						images: 'https://cdn.uviewui.com/uview/common/logo.png',
						show: false
					},

				],
				disabled: false,
				btnWidth: 180,
				show: false,
				options: [{
						text: '收藏',
						style: {
							backgroundColor: '#007aff'
						}
					},
					{
						text: '删除',
						style: {
							backgroundColor: '#dd524d'
						}
					}
				]
			}
		},
		methods: {
			markInfo() {
				uni.navigateTo({
					url: '../carInfo/carInfo'
				})
			},
			goList (){
				uni.navigateTo({
					url: './carList'
				})
			}
		}
	}
</script>

<style scoped lang="scss">
	.item {
		display: flex;
		padding: 20rpx;
	}

	image {
		width: 120rpx;
		flex: 0 0 120rpx;
		height: 120rpx;
		margin-right: 20rpx;
		border-radius: 12rpx;
	}

	.myCar {
		padding: 0 30rpx;
		display: flex;
		justify-content: space-between;
		color: #3C3C5A;
		font-size: 36rpx;
		font-weight: 600;
	}

	.u-line-2 {
		color: #3C3C5A;
		font-size: 35rpx;
		font-weight: 600;
	}

	.item_content {
		color: #999999 !important;
		font-size: 24rpx !important;
		font-weight: 400;
	}

	.title {
		text-align: left;
		font-size: 28rpx;
		color: $u-content-color;
		margin-top: 10rpx;
	}

	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		width: 100%;

		.wrap {
			width: 100%;
		}

		.wrap_bottom {
			width: 100%;
			padding: 30rpx;
			display: flex;
			justify-content: space-between;

			.wrap_bottom_items {
				display: flex;
				justify-content: space-between;
				flex-direction: column;
				align-items: center;
				color: #3C3C5A;
				font-weight: 600;
			}
		}

		.wrap_bottom_Btn {
			margin: 20rpx;
			width: 690rpx;
			text-align: center;
			height: 88rpx;
			line-height: 88rpx;
			background-color: #0072FF;
			color: #fff;
			font-size: 25rpx;
		}

		.home_title {
			width: 100%;
			padding: 0 30rpx;
			color: #89899B;
			font-size: 22rpx;

			.home_tltle_header {
				color: #3C3C5A;
				font-size: 44rpx;
				font-weight: 600;
				padding-bottom: 20rpx;
			}
		}

		.home_intro {
			color: #6E6F76;
			font-size: 22rpx;
			padding: 20rpx 0;

			.txt_left {
				text-align: left;
				padding-left: 20rpx;
				font-size: 27rpx;
				font-weight: 600;
			}

			.txt_txt {
				text-align: left;
				padding-left: 20rpx;
				font-weight: 400;
			}

		}
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
