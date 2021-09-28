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
			<view class="discover_body_content">
				<view class="discover_body_content_item">
					<p style="color:#3C3C5A ;font-size:36rpx ;">求租川崎（KAWASAKI）摩托车</p>
					<p>求租川崎（KAWASAKI）摩托车，大致租用5-7天，需要外出至 杭州时使用，有的联系，谢谢！</p>
					<div class="discover_body_content_footer">
						<span style="display: flex;">
							<p style="margin: 0;">
								<image src="../static/missing-face.png" style="width: 27rpx;height: 27rpx;"></image>
							</p>
							<span>176***6955</span>
						</span>
						<span>
							<image src="../static/missing-face.png" style="width: 27rpx;height: 27rpx;"></image>
							<span>分享</span>
						</span>
						<span>
							<image src="../static/missing-face.png" style="width: 27rpx;height: 27rpx;"></image>
							<span>6</span>
						</span>
						<span>
							<image src="../static/missing-face.png" style="width: 27rpx;height: 27rpx;"></image>
							<span>567</span>
						</span>

					</div>
				</view>
			</view>
		</view>

		<tabBar :pagePath="'/pages/discover/index'"></tabBar>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				isFinished: false
			}
		},
		methods: {
			ChangeType(value) {
				console.log('value', value)
				this.isFinished = value

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

				.discover_body_content_item {
					color: #89899B;
					font-size: 24rpx;

					p {
						margin: 10rpx 0;
					}

					.discover_body_content_footer {
						display: flex;
						justify-content: space-between;
						font-size: 27rpx;
					}
				}
			}
		}
	}
</style>
