<template>
	<view class="content">
		<div class="back"></div>
		<div class='discover_title'>
			<p>
				发现需求
			</p>
			<span>随时随地发现你想要的</span>
		</div>
		<view class="discover_body">
			<view class="discover_body_title">
				<ul
					style="display: flex; justify-content: flex-start;color:#C4C4CD ;font-size:48rpx ;font-weight: 600;">
					<li :class="!isFinished?'active':''" @click="ChangeType(false)">广场</li>
					<li @click="ChangeType(true)" :class="isFinished?'active':''">我的</li>
				</ul>
			</view>
			<view class="discover_body_content" v-show="!isShow">
				<navigator url="../../component/discover/descover_detail" hover-class="navigator-hover">
					<view class="discover_body_content_item">
						<p class="content_item_title">求租川崎（KAWASAKI）摩托车</p>
						<p>求租川崎（KAWASAKI）摩托车，大致租用5-7天，需要外出至 杭州时使用，有的联系，谢谢！</p>
						<div class="discover_body_content_footer">
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>176***6955</span>
							</span>
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>分享</span>
							</span>
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>1</span>
							</span>
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>567</span>
							</span>

						</div>
					</view>
				</navigator>
				<navigator url="../../component/discover/descover_detail" hover-class="navigator-hover">

					<view class="discover_body_content_item">
						<p class="content_item_title">赛科龙RX6SR650谁有，需要、需要、需要、急需、急需</p>
						<p>需要一辆赛科龙RX6SR650、使用期限为12天，主要用于赛事 使用需要配置高一些的，不要太旧，最好为新车，费用都可商 量，急</p>
						<div class="discover_body_content_footer">
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>176***6955</span>
							</span>
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>分享</span>
							</span>
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>1</span>
							</span>
							<span class="footer_item">
								<span>
									<image src="../static/missing-face.png" style="width: 30rpx;height: 30rpx;"></image>
								</span>
								<span>567</span>
							</span>

						</div>
					</view>
				</navigator>
			</view>
			<view class="discover_body_content" v-show="isShow">
				<div class="discover_body_content_no">
					<image src="../../static/discover/no_data.png" style="width: 360rpx;height: 240rpx;"></image>
					<p>您还没有发过帖子哦</p>
				</div>
			</view>
		</view>
		<view class="btn">
			<u-button shape="circle" type="default" @click="addDiscover">发帖 <u-icon name="plus" color="#2979ff"
					size="42"></u-icon>
			</u-button>
		</view>
		<tabBar :pagePath="'/pages/discover/index'"></tabBar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isFinished: false,
				isShow: false
			}
		},
		methods: {
			ChangeType(value) {
				console.log('value', value)
				this.isFinished = value

			},
			addDiscover() {
				uni.navigateTo({
					url: '../../component/discover/new_discover'
				});
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
		padding: 0 30rpx;
		position: relative;

		.back {
			height: 88rpx;
			line-height: 88rpx;
			background-color: #fff;
		}

		.active {
			border-bottom: #0072FF 2px solid;
			color: #3C3C5A;
		}

		.discover_title {
			color: #3C3C5A;
			font-size: 60rpx;
			font-weight: 600;

			span {
				font-size: 30rpx;
				color: #89899B;
			}
		}

		.discover_body {
			margin-top: 30rpx;

			height: calc(100% - 124px);

			.discover_body_title {
				ul {
					padding: 0;

					li {
						margin-right: 20rpx;
					}
				}
			}

			.discover_body_content {
				margin-top: 20rpx;
				position: relative;
				height: 100%;

				.discover_body_content_no {
					margin: auto;
					text-align: center;
					position: relative;
					top: 30%;
					transform: translateY(-30%);
					color: #848389;
				}

				.discover_body_content_item {
					color: #89899B;
					font-size: 24rpx;
					padding: 20rpx 0;

					.content_item_title {
						color: #3C3C5A;
						font-size: 36rpx;
						width: 690rpx;
						overflow: hidden;
						text-overflow: ellipsis;
						white-space: nowrap;
					}

					p {
						margin: 10rpx 0;
					}

					.discover_body_content_footer {
						display: flex;
						justify-content: space-between;
						font-size: 27rpx;

						.footer_item {
							display: flex;
							height: 30rpx;
							line-height: 30rpx;
							font-size: 20rpx;
						}
					}
				}
			}
		}

		.btn {
			position: fixed;
			bottom: 120rpx;
			left: 50%;
			transform: translateX(-50%);

			uni-button {
				border-radius: 20px;
				box-shadow: 1px 1px 2px 2px #eee;
				background-color: #fff;
				padding: 0 60rpx;
				color: #0072FF;
				font-weight: 600;
			}
		}
	}
</style>
