<template>
	<view class="content">
		<div class="title">常用小工具</div>
		<div class="serivce">
			<div class="sericeItem">
				<img src="../static/mine/line-service.png" style="width:20px;height: 20px;"></img>
				<p>在线客服</p>
			</div>

			<div class="sericeItem">
				<navigator url="../../component/Driver/Driver_list" hover-class="navigator-hover">
					<img src="../static/mine/driver.png" style="width:20px;height: 20px;"></img>
					<p>常用驾驶人</p>
				</navigator>
			</div>

			<div class="sericeItem">
				<navigator url="../../component/advise/advise" hover-class="navigator-hover">

					<img src="../static/mine/advise.png" style="width:20px;height: 20px;"></img>
					<p>意见反馈</p>					
					</navigator>
			</div>
		</div>
	</view>
</template>

<script>
</script>

<style lang="scss" scoped>
	.content {

		margin: auto 10px;
		height: 200rpx;
		border-radius: 5px;
		background-color: #fff;
		box-shadow: 0 0 5px #a6a6a6;
		color: #3B3B59;

		.title {
			font-size: 32rpx;
			font-weight: 700;
			padding: 24rpx 0 0 24rpx;
		}

		.serivce {
			display: flex;
			justify-content: space-around;
			align-items: center;
			padding: 24rpx 0;

			.sericeItem {
				text-align: center;
			}
		}
	}
</style>
