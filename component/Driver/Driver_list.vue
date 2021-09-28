<template>
	<view class="content">
		<view class="driver_list">
			<div class="list_no">
				<image src="../../static/mine/driver/contacts.png" mode=""></image>
				<p style="color: #3B3B59;font-size: 29rpx;padding: 20rpx;">请添加常用驾驶人信息</p>
				<p style="color: #848389;font-size: 27rpx;width: 600rpx;">
					您可以添加他人作为常用驾驶人，并进行 管理，以便用车时选择添加
				</p>
			</div>
			
		</view>
		<view class="btn_btm">		
			<u-button type="primary" @click="addContact()">添加常用驾驶人</u-button>
		</view>
	</view>
</template>

<script>
	export default {
		data () {
			return {}
		},
		methods: {
			addContact(){
				uni.navigateTo({
				    url: '/component/Driver/Driver_new'
				});
			}
		}
	}
</script>

<style lang="scss" scoped>
	 page{
		 height: 100%;
	 }
	 .content {
		 height: 100%;
		 position: relative;
		 .driver_list {
			 position: relative;
			 height: 100%;
			 .list_no {
			 		position: absolute;
					left: 50%;
					top:50%;
					transform: translate(-50%,-50%);
					text-align: center;
					image {
						width: 140rpx;
						height: 152rpx;
					}
			 }
		 }
		 
		 .btn_btm {
			 width: 690rpx;
			 margin: auto 0;
			 position: fixed;
			 left: 50%;
			 bottom: 40rpx;
			 transform: translateX(-50%);
		 }
	 }
</style>
