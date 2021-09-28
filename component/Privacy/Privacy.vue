<template>
	<view class="content">
		<div class="back">
			<navigator url="../../pages/perfer/index" hover-class="navigator-hover"
				style="display: inline-block; float: left;">
				<image src="../../static/tab/back.png" mode="" class="header_back" style="width: 17rpx;height: 30rpx;">
				</image>
			</navigator>
			<span> 隐私 </span>
		</div>
		<view class="perfer_content">
			<view class="perfer_body_contact">
				<navigator url="./policy" hover-class="navigator-hover">
					<div class="perfer_body_items">
						<span>隐私设置</span>
						<navigator url="changeMobile" hover-class="navigator-hover">
							<span class="items_replenish" style="display: flex;">
								<span>

								</span>
								<p>
									<image src="../../static/preference/preference/next.png" mode="aspectFit"
										style="width: 27rpx;height: 27rpx; vertical-align: middle;padding-left: 20rpx;">
									</image>

								</p>
							</span>
						</navigator>
					</div>
				</navigator>
				<navigator url="./perfer" hover-class="navigator-hover">
					<div class="perfer_body_items">
						<span>隐私政策</span>
						<span class="items_replenish" style="display: flex;">
							<span>

							</span>
							<p>
								<image src="../../static/preference/preference/next.png" mode="aspectFit"
									style="width: 27rpx;height: 27rpx; vertical-align: middle;padding-left: 20rpx;">
								</image>

							</p>
						</span>
					</div>
				</navigator>
			</view>



		</view>
		<u-modal v-model="show" :content="content" show-cancel-button confirm-text="确认解绑"></u-modal>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show: false,
				content: '您确认要从当前账号解绑微信么?'
			}
		},
		methods: {
			UnboundWeChat() {
				this.show = true;
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
		background-color: #F3F3F3;
		position: relative;

		.back {
			height: 88rpx;
			line-height: 88rpx;
			text-align: center;
			font-size: 36rpx;
			position: relative;
			background-color: #fff;

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


				.perfer_body_items {
					justify-content: space-between;
					display: flex;
					color: #3C3C5A;
					font-size: 27rpx;
					padding: 30rpx ;
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
