<template>

	<view class="content" :style="{'background': noData?'#fff':'#F3F3F3','padding':noData?' 0 30rpx':'0'}">
		<div class="back" :style="{'background': noData?'#F6F6F6':'#fff'}">
			<navigator url="../../pages/perfer/index" hover-class="navigator-hover" style="display: inline-block; float: left;">
				<image v-if="noData" src="../../static/tab/back_white.png" mode="aspectFill" class="header_back"> </image>
				<image v-if="!noData" src="../../static/tab/back.png" mode="aspectFill" class="header_back"> </image>

			</navigator>
			<span>紧急联系人</span>
		</div>
		<view class="no_contact" v-if="noData">
			<div>
				<image src="../../static/mine/no_contact.png" mode="aspectFit" style="width: 200rpx;height: 100rpx;">
				</image>
				<p>您还没有添加紧急联系人哦</p>
				<p style="color: #848389;font-size: 26rpx;">为了保证您的行程安全，请至少添加1位紧急 联系人，别让您最爱的人担心</p>
			</div>
		</view>
		<view class="yes_contact" v-if="!noData">
			<p style="padding: 10rpx 30rpx;">为了保证您的行程安全，请至少添加1位紧急联系人，别让 您最爱的人担心</p>
			<div
				style="line-height: 90rpx;height: 90rpx;display: flex;justify-content: space-between;background-color: #fff; padding: 0 30rpx;">
				<span>林小姐</span>
				<navigator url="changeMobile" hover-class="navigator-hover">
					<span class="items_replenish" style="display: flex;">
						<p>
							<image src="../../static/preference/preference/next.png" mode="aspectFit"
								style="width: 27rpx;height: 27rpx; vertical-align: middle;padding-left: 20rpx;">
							</image>

						</p>
					</span>
				</navigator>
			</div>
		</view>
		
		<button class="btn" type="primary" @click="addContact">添加紧急联系人</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				noData: false
			}
		},
		methods: {
			addContact () {
				uni.navigateTo({
				    url: 'addContact'
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
		position: relative;

		.back {
			height: 88rpx;
			line-height: 88rpx;
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

		.no_contact {
			position: absolute;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
			text-align: center;

			p {
				color: #3C3C5A;
				font-size: 29rpx;
				width: 690rpx;
				padding: 10rpx 0;
			}
		}

		.btn {
			position: fixed;
			bottom: 30rpx;
			width: 690rpx;
		}
	}
</style>
