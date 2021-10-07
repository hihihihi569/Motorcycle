<template>
	<view class="content">
		<header>全部评论</header>
		<div>
			<view class="artcle">


				<view class="artcle_title">
					<span>
						<image src="../../static/missing-face.png" mode="aspectFit" style="width: 75rpx;height: 75rpx;">
						</image>
					</span>
					<div>
						<p>139****1114</p>
						<p style="color: #89899B;font-size: 20rpx;">5天前</p>
					</div>
				</view>
				<div class="right_p">
					<image src="../../static/tab/message.png" mode="aspectFit" style="width: 50rpx;height: 50rpx;">
					</image>
				</div>
			</view>
			<view class="comment">
				<p>欲租从速，过期不候，日租金999999元。</p>
			</view>
		</div>
		<view class="comment_input">
			<view><input type="text" value="" placeholder="说说你的想法..."/></view>
			<view>
				
				<span >
					<image src="../../static/tab/message.png" mode="aspectFit" style="width: 40rpx;vertical-align: middle;height: 38rpx;"></image>
				</span>
				<span>23</span>
				</view>
		    <view>
				<span >
					<image src="../../static/home/collection.png" mode="aspectFit" style="width: 40rpx;vertical-align: middle;height: 38rpx;"></image>
				</span>
				<span>26</span>
			</view>
		
		</view>
	</view>
</template>

<script>
</script>

<style lang="scss" scoped>
	.content {
		margin-top: 20rpx;
		header {
			color: #3C3C5A;
			font-size: 38rpx;
			background-color: #fff;
			padding-bottom: 20rpx;
		}

		.artcle {
			display: flex;
			justify-content: space-between;
			padding: 0 30rpx;
			background-color: #fff;

			.artcle_title {
				display: flex;
				justify-content: flex-start;

				span {
					margin-right: 20rpx;
				}

				.right_p {
					float: right;
				}

				p {
					color: #3C3C5A;
					font-size: 25rpx;
				}
			}
		}

		.comment {
			padding: 0 30rpx 0 120rpx;
			background-color: #fff;
		}
.comment_input {
    position: fixed;
	bottom: 40rpx;
	padding: 0 30rpx;
    width: 100%;
	background-color: #fff;
	display: flex;
	justify-content: space-between;
	height: 62rpx;
	line-height: 62rpx;
	input {
		background-color: #F6F6F6;
		color: #999999;
		font-size: 20rpx;
		width: 400rpx;
		height: 62rpx;
	}
}
	}
</style>
