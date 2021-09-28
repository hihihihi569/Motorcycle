<template>
	<view class="content">
		<ul style="display: flex; justify-content: space-evenly; margin: 30rpx auto; padding: 0;">
			<li :class="!isFinished?'active':''" @click="ChangeType(false)">待处理</li>
			<li @click="ChangeType(true)" :class="isFinished?'active':''">已完成</li>
		</ul>
		<view class="list_nodata" v-if="!isFinished">
			<image src="../../static/mine/violation/Violation_will.png" mode=""></image>
			<p>
				您没有未处理的违章哦
			</p>
		</view>
		<view class="list_nodata"  v-else="isFinished">
			<image src="../../static/mine/violation/Violation_finsh.png" mode=""></image>
			<p>
				无已完成的违章记录
			</p>
		</view>
	</view>
</template>

<script>
export default {
	data () {
		return {
			isFinished:false
		}
	},
	methods:{
		ChangeType(value) {
			console.log('value',value)
			this.isFinished=value
			
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
		.active {
			border-bottom:  #0072FF 2px solid ;
		}
		.list_nodata {
			position: absolute;
			left: 50%;
			bottom: 50%;
			transform: translate(-50%,50%);
			text-align: center;
			image {
				width: 350rpx;
				height: 160rpx;
			}
			p {
				font-size: 27rpx;
				color: #848389;
			}
		}
	}
</style>
