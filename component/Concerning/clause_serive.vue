<template>
	<view class="content">
		<div class="back">
			<navigator url="./concerning" hover-class="navigator-hover">
				<image src="../../static/tab/back.png" mode="aspectFit" style="width: 18rpx;height: 36rpx;"></image>
			</navigator>
		</div>
		<div>
			<div class="header">
				摩托圈租车平台服务规则
			</div>
			<div class="title">
				
				<p style="color: #3B3B59;font-size: 32rpx;font-weight: 600; padding: 30rpx 0;">
					平台服务规则
				</p>

			</div>
			<div class="note_content">
				<p style="font-size: 26rpx;font-weight: 600;">尊敬的摩托圈用户： </p>

				<p style="text-indent: 2em;"> 我们对《摩托圈隐私政策》进行了更新。此版本更新主要集中在摩托圈需要收集的您个人信息的种类以及您 </p>
			

				<p>请确保所有的交易已完结且无纠纷，账户删除后的历史 交易可能会丢失，后期将无法申诉维权。</p>
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
