<template>
	<view class="content">
		<div class="back">
			<navigator url="./Privacy" hover-class="navigator-hover" style="display: inline-block; float: left;">
				<image src="../../static/tab/back.png" mode="" class="header_back" style="width: 17rpx;height: 30rpx;">
				</image>
			</navigator>
			<span>隐私设置</span>
		</div>
		<view class="perfer_content">
			<view class="perfer_body_contact">
				<div class="perfer_body_items">
					<span>开启地理位置定位</span>
					<!-- <navigator url="changeMobile" hover-class="navigator-hover"> -->
					<span class="items_replenish" style="display: flex;">
						<span>
							已开启
						</span>
						<p>
							<image src="../../static/preference/preference/next.png" mode="aspectFit"
								style="width: 27rpx;height: 27rpx; vertical-align: middle;padding-left: 20rpx;">
							</image>

						</p>
					</span>
				</div>
				<p class="perfer_body_items_explain">根据您的位置推荐您周围的车辆。关于<a>《位置信息》</a></p>
				<div class="perfer_body_items">
					<span>允许摩托圈访问相机</span>
					<span class="items_replenish" style="display: flex;">
						<span>
							去设置
						</span>
						<p>
							<image src="../../static/preference/preference/next.png" mode="aspectFit"
								style="width: 27rpx;height: 27rpx; vertical-align: middle;padding-left: 20rpx;">
							</image>

						</p>
					</span>
				</div>
				<p class="perfer_body_items_explain">实现扫码、拍照、与上传。关于<a>《访问相机》</a></p>
				<div class="perfer_body_items">
					<span>允许摩托圈访问通讯录</span>
					<span class="items_replenish" style="display: flex;">
						<span>
							去设置
						</span>
						<p>
							<image src="../../static/preference/preference/next.png" mode="aspectFit"
								style="width: 27rpx;height: 27rpx; vertical-align: middle;padding-left: 20rpx;">
							</image>

						</p>
					</span>
				</div>
				<p class="perfer_body_items_explain">方便您租车时取用您的联系人信息。关于<a>《通讯录信息》</a></p>
				<div class="perfer_body_items">
					<span>允许摩托圈访问相册</span>
					<span class="items_replenish" style="display: flex;">
						<span>
							去设置
						</span>
						<p>
							<image src="../../static/preference/preference/next.png" mode="aspectFit"
								style="width: 27rpx;height: 27rpx; vertical-align: middle;padding-left: 20rpx;">
							</image>

						</p>
					</span>
				</div>
				<p class="perfer_body_items_explain">实现您图片的取用与上传。关于<a>《访问相册》</a></p>

			</view>



		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				username: ''
			}
		},
		methods: {
			submit() {
				console.log('提交')
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
		width: 100%;
		background-color: #F3F3F3;
		position: relative;

		.back {
			height: 88rpx;
			line-height: 88rpx;
			background-color: #fff;
			text-align: center;
			font-size: 36rpx;
			position: relative;

			.header_back {
				width: 18rpx;
				height: 36rpx;
				position: absolute;
				left: 36rpx;
				top: 50%;
				transform: translateY(-50%);
			}
		}

		.perfer_content {
			.perfer_body_contact {
				background-color: #FFFFFF;
				margin: 20rpx 0;

				.perfer_body_items_explain {
					background: #F3F3F3;
					padding: 15rpx 0 45rpx 0;
					text-align: center;
					color: #89899B;
					font-size: 25rpx;

					a {
						color: #0072FF;
					}
				}

				.perfer_body_items {
					justify-content: space-between;
					display: flex;
					color: #3C3C5A;
					font-size: 30rpx;
					padding: 30rpx 30rpx;
					border-bottom: 1px solid #EEEEEE;

					.items_replenish {
						color: #89899B;
						font-size: 19rpx;
					}

				}
			}
		}


	}
</style>
