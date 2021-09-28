<template>
	<view class="content">
		<div class="back">
			<navigator url="secure" hover-class="navigator-hover">
				<image src="../../static/tab/back.png" mode="aspectFit" style="width: 18rpx;height: 36rpx;"></image>
			</navigator>
		</div>
		<div>
			<div class="header">
				注销账号
			</div>
			<div class="title">
				<p>
					<image src="../../static/preference/preference/cancellation.png" mode="aspectFit"
						style="width: 100rpx;height: 100rpx;"></image>
				</p>
				<p style="color: #3B3B59;font-size: 32rpx;font-weight: 600; padding: 30rpx 0;">
					将176****6955所绑定的账号注销
				</p>

			</div>
			<div class="note_content">
				<p style="font-size: 26rpx;font-weight: 600;">注意：注销帐号后以下信息将被清空且无法找回</p>

				<p>· 身份、账户信息及其他权益信息 </p>
				<p>· 交易记录、历史订单</p>
				<p>· 收藏、聊天内容</p>

				<p>请确保所有的交易已完结且无纠纷，账户删除后的历史 交易可能会丢失，后期将无法申诉维权。</p>
			</div>
		</div>
		<div style="padding: 20rpx 0;">
			<u-input v-model="value" type="textarea" style="background-color: #F2F2F2;text-align: left;padding: 10rpx 30rpx ;" height="100" auto-height placeholder="请填写注销原因（必填），展现独一无二的你~"/>
			<div style="width: 100%;padding: 30rpx 0;text-align: center;">
				
				<button type="primary">提交申请</button>
				<p style="font-size: 24rpx;padding: 20rpx 0;">点击【提交申请】即代表你已经同意 <a style="color: #0072FF;">《用户注销协议》</a></p>
			</div>
		</div>
	</view>
</template>

<script>
	export default {
		data () {
			return {
				value:''
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
		padding: 0 30rpx;

		.back {
			height: 88rpx;
			line-height: 88rpx;
			background-color: #fff;
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
			border: 1px solid #EEEEEE;
			border-radius: 5px;
			padding: 20rpx;
			p {
				padding: 20rpx 0;
				color: #89899B;
				font-size: 26rpx;
			}
		}
	}
</style>
