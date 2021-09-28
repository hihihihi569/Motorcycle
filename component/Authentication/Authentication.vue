<template>
	<view class="content">
		<div class="notes">
			您可以上传身份证照片自动识别，或手动填写
		</div>
		<view class="Id_card">
			<view class="Id_card_img">
				<image src="../../static/mine/idcard/id_card.png" mode=""></image>
				<div>上传身份证</div>
			</view>
		</view>
		<view class="input_Idcard">
			<form @submit="formSubmit" @reset="formReset">
				<view class="uni-form-item uni-column">
					<view class="title">姓名</view>
					<view>
						<input type="text" placeholder="请输入您的姓名" class="name_input" />
						<!-- <input v-else  type="number"  placeholder="请输入数字" /> -->
					</view>
				</view>
				<hr>
				<view class="uni-form-item uni-column">
					<view class="title">身份证号</view>
					<view>
						<input type="text" placeholder="请输入您的身份证号" class="name_input" style="border: none;" />
						<!-- <input v-else  type="number"  placeholder="请输入数字" /> -->
					</view>
				</view>
				  <view class="uni-btn-v">
				                    <button form-type="submit" type="primary">确认提交</button>
									<a href="#" style="color: #0072FF;">港澳台及海外用户认证入口 ></a>
				                    <!-- <button type="default" form-type="reset">重置</button> -->
				   </view>
			</form>
		</view>
	</view>
</template>

<script>
</script>

<style lang="scss" scoped>
	.content {
		background-color: #fff;
		text-align: center;
		height: 100%;

		.notes {
			margin: 20rpx auto;
			padding-top: 20rpx;
		}

		.Id_card {
			width: 690rpx;
			height: 410rpx;
			background-color: #F6F6F6;
			margin: auto;
			border: 1px soild #D3D3D3;
			border-radius: 5px;
			position: relative;

			.Id_card_img {
				position: absolute;
				left: 50%;
				top: 50%;
				transform: translate(-50%, -50%);
				image {
					width: 80rpx;
					height: 70rpx;
				}
			}

		}

		.input_Idcard {
			width: 690rpx;
			margin: auto;
			.title {
				margin: 30rpx 0;
				color: #89899B;
				text-align: left;
				font-weight: 700;
				font-size: 28rpx;
			}
			.name_input {
				color: #D8D8D8;
				text-align: left;
				font-size: 32rpx;
				margin: 30rpx 0;
			}
			.uni-btn-v {
				margin: 40rpx 0;
				button {
					height: 3.33*2 rpx;
					margin: 30rpx 0;
				}
				a {
				}
			}
		}
	}
</style>
