<template>
	<view class="content">
		<div class="title">暖心服务</div>
		<div class="serivce">
			<div class="sericeItem">
				<navigator url="../../component/Violation/Violation" hover-class="navigator-hover">
					<img src="../static/mine/Violation.png" style="width:20px;height: 20px;"></img>
					<p>违章专区</p>
				</navigator>
			</div>

			<div class="sericeItem">
				<div @click="open()">
					<img src="../static/mine/download.png" style="width:20px;height: 20px;"></img>
					<p>租赁合同下载</p>
					
				</div>
			</div>

			<div class="sericeItem">
				<navigator url="../../component/Authentication/Authentication" hover-class="navigator-hover">
					<img src="../static/mine/present.png" style="width:20px;height: 20px;"></img>
					<p>邀请有礼</p>
				</navigator>
			</div>
		</div>
		<u-modal v-model="show" :title-style="{color: '#3B3B59',fontSize:'30rpx',paddingBottom: '32rpx'}" confirm-text="确认下载" :cancel-style="{color:'#AAAAB0',backgroudColor:'#F1F1F1',borderRadius:'25%'}" show-cancel-button title='温馨提示'>
					<view class="slot-content">
						<rich-text :nodes="content"></rich-text>
					</view>
		</u-modal>
	</view>
</template>

<script>
	export default {
			data() {	
				return {
					show: false,
					content: '点击下载后，合同将直接保存至您的手机'
				}
			},
			methods: {
				open() {
					this.show = true;
				}
			}
		}
</script>

<style lang="scss" scoped>
	.content {
		margin: auto 10px;
		height: 200rpx;
		border-radius: 5px;
		background-color: #fff;
		box-shadow: 0 0 5px #a6a6a6;
		margin-bottom: 30rpx;
		margin-top: 30rpx;

		color: #3B3B59;

		.title {
			padding: 24rpx 0 0 24rpx;
			font-size: 32rpx;
			font-weight: 700;
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
		.slot-content {
			font-size: 27rpx;
			text-align: center;
			padding-bottom: 30rpx;
		}
	}
</style>
