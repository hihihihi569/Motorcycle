<template>
	<view class="content">

		<div class="back">
			<navigator url="../../pages/discover/index" hover-class="navigator-hover">
				<image src="../../static/tab/back.png" mode="" class="header_back" style="width: 17rpx;height: 30rpx;">
				</image>
			</navigator>
			<span> 发帖 </span>
			<a>发布</a>
		</div>
		<view class="new_body">
			<u-form :model="form" ref="uForm">
				<u-form-item>
					<u-input v-model="form.title" placeholder="标题4-40字（必填）" />
				</u-form-item>
				<u-form-item>
					<u-input v-model="form.intro" placeholder="这一刻说点什么吧~" type="textarea" border auto-height height="100"/>
				</u-form-item>

			</u-form>
			<view class="body_footer">
				<a>
					<image src="../../static/discover/pic.png" mode="aspectFit" style="width: 50rpx;height: 50rpx;">
					</image>
				</a>
				<a>
					<image src="../../static/discover/expression.png" mode="aspectFit"
						style="width: 50rpx;height: 50rpx;"></image>
				</a>
			</view>
			<view class="footer">
				<p>
					请注意：
				</p>
				<p>
					1. 摩摩提醒：请勿发布带含有联系方式、营销推广、色情或暴力 等违法违规的图片、文字、或链接。
				</p>
				<p>
					2. 为了维护良...
				</p>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				form: {
					title: '',
					intro: '',
				},
			}
		}
	}
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
	}

	.content {
		height: 100%;
		background-color: #fff;
		position: relative;

		.back {
			height: 88rpx;
			line-height: 88rpx;
			text-align: center;
			font-size: 36rpx;
			position: relative;
			background-color: #F6F6F6;

			display: flex;
			justify-content: space-between;
			padding: 0 30rpx;

			.header_back {
				width: 18rpx;
				height: 36rpx;

			}

			a {
				color: #0072FF;
			}
		}

		.new_body {
			padding: 0 30rpx;

			.body_footer {
				display: flex;
				justify-content: flex-start;

				a {
					padding: 30rpx;
				}
			}
		}
		.footer {
			color: #89899B;
			font-size: 24rpx;
		}
	}
</style>
