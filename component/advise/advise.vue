<template>
	<view class="content">
		<view class="form">
			<u-form :model="form" ref="uForm">
				<u-form-item>
					<u-checkbox-group wrap>
						<u-checkbox class="form_select" shape="circle" v-model="item.checked"
							v-for="(item, index) in checkboxList" :key="index" :name="item.name">
							{{ item.name }}
						</u-checkbox>
					</u-checkbox-group>
				</u-form-item>
			</u-form>
		</view>
		<view class="file_img">
			<p>您也可以上传相关问题照片（选填）</p>
			<view class="file_img_add">
				<div class="file_img_items">
					<div>
						<image src="../../static/mine/feedback/faceback_img.png" mode="aspectFit"
							style="width: 50rpx;height: 50rpx;"></image>
						<p>上传图片</p>
					</div>
				</div>
			</view>

		</view>
		<view class="file_img">
			<p>您的手机号（选填）</p>
			<u-input v-model="value" type="text" placeholder='请输入您的手机号' style="border-bottom: 0.5px solid #EEEEEE;"/>
			
		<u-button  type="primary" @click="submit">确认提交</u-button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				form:{
					
				},
				value:'',
				checkboxList: [{
						name: '找车问题',
						checked: false,
						disabled: false
					},
					{
						name: '下单问题',
						checked: false,
						disabled: false
					},
					{
						name: '支付问题',
						checked: false,
						disabled: false
					}, {
						name: '订单问题',
						checked: false,
						disabled: false
					}, {
						name: '车主端问题',
						checked: false,
						disabled: false
					}, {
						name: '其他问题及建议',
						checked: false,
						disabled: false
					}
				],
				switchVal: false
			};
		},
		methods:{
			submit(){
				console.log('提交')
			}
		}
	
	};
</script>
<style lang="scss" scoped>
	page {
		height: 100%;
	}

	.content {
		height: 100%;
		background-color: #F7F7F7;
		.form {
			background-color: #fff;
			padding: 0 15rpx;
		}

		.u-form-item {
			padding: 0;
		}

		.form_select {
			border-bottom: 1px solid #EEEEEE;
			padding: 15rpx 0;
		}

		.file_img {

			background-color: #fff;
			margin: 30rpx 0 0 0;
			padding: 0 30rpx;
			p {
				padding: 30rpx 0;
				color: #3B3B59;
				font-size: 29rpx;
				font-weight: 700;
			}
			.file_img_add {
				display: flex;
				justify-content: flex-start;

				.file_img_items {
					height: 187.5rpx;
					width: 187.5rpx;
					border: 0.5px solid #CBCBCB;
					border-radius: 2px;
					position: relative;
					text-align: center;

					// vertical-align: middle;
					div {
						position: relative;
						top: 50%;
						left: 50%;
						transform: translate(-50%, -50%);

						p {
							padding: 10rpx 0;
							width: 187.5rpx;
							color: #D8D8D8;
						}
					}
				}
			}
		}
	}
</style>
