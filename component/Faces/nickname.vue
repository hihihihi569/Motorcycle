<template>
	<view class="content">
		<div class="back">
			<navigator url="./face" hover-class="navigator-hover" style="display: inline-block; float: left;">
				<image src="../../static/tab/back.png" mode="" class="header_back" style="width: 17rpx;height: 30rpx;">
				</image>
			</navigator>
			<span>设置昵称</span>
		</div>
		<div class="nick_items">			
			<input type="text" v-model="username" placeholder="请输入您的昵称" clearable="true"/>
		</div>
		<div>			
			<button type="primary" @click="submit">确定</button>
		</div>
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
		.nick_items {
			background-color: #fff;
			margin:  20rpx 0;
			padding: 0 30rpx;
			height: 100rpx;
			line-height: 100rpx;
			position: relative;
			input {
				position: absolute;
				top: 50%;
				transform: translateY(-50%);
			}
		}
	}
</style>
