<template>

	<view class="content" >
		<div class="back">
			<navigator url="./contactList" hover-class="navigator-hover" >
				<image src="../../static/preference/preference/close.png" mode="aspectFill" class="header_back"> </image>
			</navigator>
		</div>
		<div>
			<div class="header">
				请填写紧急联系人信息
			</div>
			
			<u-form :model="form" ref="uForm">
				<u-form-item prop="name" label="姓名" label-width="240rpx" style="color: #89899B;" >
					<u-input v-model="form.name" placeholder="请输入姓名" />
					<image src="../../static/mine/driver/name.png" mode="aspectFit" style="width: 36rpx; height: 36rpx; ">
					</image>
				</u-form-item>
				<u-form-item prop="mobile" label="手机号" label-width="240rpx" style="color: #89899B;">
					<u-input v-model="form.mobile"  placeholder="请输入手机号"/>
				</u-form-item>
			</u-form>
			<div class="submit">
				
				<u-button type="primary" @click="submit">完成 </u-button>
			</div>
		</div>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				noData: false,
				form:{
					name:'',
					mobile:''
				},
				rules: {
						name: [{
							required: true,
							message: '请输入姓名',
							// 可以单个或者同时写两个触发验证方式 
							trigger: ['change', 'blur'],
						}],
						mobile: [{
								required: true,
								message: '请输入手机号',
								trigger: ['change', 'blur'],
							},
							{
								// 自定义验证函数，见上说明
								validator: (rule, value, callback) => {
									// 上面有说，返回true表示校验通过，返回false表示不通过
									// this.$u.test.mobile()就是返回true或者false的
									return this.$u.test.mobile(value);
								},
								message: '手机号码不正确',
								// 触发器可以同时用blur和change
								trigger: ['change', 'blur'],
							}
						],			
						
					}
				
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
		padding: 0 30rpx;
		.back {
			height: 88rpx;
			line-height: 88rpx;
			font-size: 36rpx;
			position: relative;
			.header_back {
				width: 36rpx;
				height: 36rpx;
				position: absolute;
				top: 50%;
				transform: translateY(-50%);
			}
		}
		.header {
			color: #3B3B59;
			font-size: 44rpx;
			font-weight: 600;
			padding-bottom: 30rpx;
			border-bottom: 1px solid #F2F2F2;
		
		
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

		.submit {
			padding: 30rpx 0;
			width: 690rpx;
		}
	}
	
</style>
