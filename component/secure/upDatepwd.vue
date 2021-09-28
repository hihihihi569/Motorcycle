<template>
	<view class="content">
		<div class="back">
			<navigator url="secure" hover-class="navigator-hover">
				<image src="../../static/tab/back.png" mode="aspectFit" style="width: 18rpx;height: 36rpx;"></image>
			</navigator>
		</div>
		<div>
			<div class="header">
				重新设置新密码
			</div>

			<div class="note_content">
				<p style="font-size: 30rpx;font-weight: 600;">176****6955</p>
				<p style="display: flex;justify-content: space-between;">
					<input type="text" placeholder="请输入验证码" v-model="code" />
					<button @click="open" type="default" :plain="true" size="mini"
						style="border: none; color: rgb(0, 114, 255); text-align: right; margin: 0; padding: 0;">获取验证码</button>
				</p>
				<p>
					<input type="text" v-model="pdw" placeholder="请确认新密码" />
				</p>
				<p>必须是6-18个英文、数字或符号(除空格),且字母、数字和标点符号 至少包含两种</p>

			</div>
		</div>
		<div style="padding: 20rpx 0;" class="mobile_btn">
			<button type="primary">确认</button>
		</div>
		<u-modal v-model="show" :mask-close-able="true" confirm-text="确认" title='请先输入图形验证码'>
			<view class="slot-content">
				<input type="text" placeholder="图形验证码" />
				<image src="../../static/mine/advise.png" style="width: 50rpx;height: 40rpx;"></image>
				<image @click="close" src="../../pages/static/preference/preference/close.png" mode="aspectFit"
					style="width: 24rpx;height: 24rpx;position: absolute;top: -60rpx; left: 30rpx;"></image>
			</view>
		</u-modal>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show: false,
				pdw: '',
				code: '',
			}
		},
		methods: {
			open() {
				this.show = true;
			},
			close() {
				this.show = false;
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
				padding: 30rpx 0;
				color: #666666;
				font-size: 26rpx;
			}
		}

		.slot-content {
			position: relative;
			padding: 30rpx;
			display: flex;
			justify-content: space-between;

			.close {
				position: absolute;
				top: -30rpx;
			}
		}
	}
</style>
