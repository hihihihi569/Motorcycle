<template>
	<view class="content">
		<div class="back">
			<navigator url="secure" hover-class="navigator-hover">
				<image src="../../static/tab/back.png" mode="aspectFit" style="width: 18rpx;height: 36rpx;"></image>
			</navigator>
		</div>
		<div>
			<div class="header">
				换绑手机号
			</div>
			<div class="title">
				<p>
					您当前的手机号是
				</p>
				<p style="color: #3B3B59;font-size: 36rpx;font-weight: 600;">
					176 2194 5955
				</p>

			</div>
			<div class="note_content">
				<p style="font-size: 30rpx;font-weight: 600;">友情提示：</p>
				<p>1.换绑流程：原手机号验证->新手机号->完成</p>
				<p>2.换绑手机后，原账号的一切信息（含订单、历史记录） 将一并导入新绑定手机号中。</p>
				<p>3.仅支持换绑到为注册过的手机号，30天内最多可换绑3 次，绑定成功后需使用新手机号登录。</p>

			</div>
		</div>
		<div style="padding: 20rpx 0; " class="mobile_btn">
			<navigator url="./update_mobile" hover-class="navigator-hover">				
				<button type="primary">更换手机号</button>
			</navigator>
		</div>
	</view>
</template>

<script>
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
	}

	.content {
		height: 100%;
		background-color: #fff;
		position: relative;
		padding: 0 30rpx;

		.back {
			height: 88rpx;
			line-height: 88rpx;
			background-color: #fff;
		}
		.mobile_btn {
			position: fixed;
			bottom: 20rpx;
			width: 690rpx;
		}
		.header {
			color: #3B3B59;
			font-size: 44rpx;
			font-weight: 600;
			padding-bottom: 30rpx;
			border-bottom: 1px solid #F2F2F2;


		}

		.title {
			width: 100%;
			text-align: center;

			p {
				color: #666666;
				font-size: 25rpx;
				padding: 20rpx 0;
			}
		}

		.note_content {
			p {
				padding: 20rpx 0;
				color: #666666;
				font-size: 26rpx;
			}
		}
	}
</style>
