<template>
	<view class="content">
		<div class="header">
			<navigator url="./Driver_list" hover-class="navigator-hover">
				<image src="../../static/tab/back.png" mode="" class="header_back"> </image>
			</navigator>
		</div>
		<div class='form_title'>
			请填写常用驾驶人信息
		</div>
		<u-form :model="form" ref="uForm">
			<u-form-item prop="name">
				<u-input v-model="form.name" placeholder="请输入姓名" />
				<image src="../../static/mine/driver/name.png" mode="aspectFit" style="width: 36rpx; height: 36rpx; ">
				</image>
			</u-form-item>
			<u-form-item prop="mobile">
				<u-input v-model="form.mobile" placeholder="请输入手机号" />
			</u-form-item>
			<u-form-item prop="Idcard">
				<u-input v-model="form.Idcard" placeholder="请输入身份证号码" />
			</u-form-item>
			<u-form-item prop="license_type">
				<u-input @click="license_isShow= true" v-model="form.license_type" placeholder="请输入准驾车型" />
				<u-select placeholder="" v-model="license_isShow" mode="single-column" :list="list" @confirm="confirm">
				</u-select>

			</u-form-item>
			<u-form-item prop="showStartTime">
				<div class="driverTime">
					<u-input @click="showStart = true" :placeholder="form.showStartTime?'驾驶证有效起始日期':'请选择驾驶证有效起始日期'"
						disable />
					<u-calendar v-model="showStart" :mode="modeStart" @change="changeStart"></u-calendar>
					<p>
						<span>{{form.showStartTime}}</span>
						<image @click="showStart = true" src="../../static/mine/driver/calendar.png" mode="aspectFit"
							style="width: 36rpx; height: 36rpx; "></image>
					</p>
				</div>

			</u-form-item>
			<u-form-item prop="showEndTime">
				<div class="driverTime">
					<u-input @click="showEnd = true" :placeholder="form.showEndTime?'驾驶证有效终止日期':'请选择驾驶证有效终止日期'"
						disable />

					<u-calendar :min-date="form.showStartTime" v-model="showEnd" :mode="mode" @change="changeEnd"></u-calendar>
					<p>
						<span>{{form.showEndTime}}</span>
						<image @click="showEnd = true" src="../../static/mine/driver/calendar.png" mode="aspectFit"
							style="width: 36rpx; height: 36rpx; "></image>
					</p>
				</div>

			</u-form-item>
		</u-form>

		<u-button type="primary" @click="submit">确认</u-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showStart: false,
				showEnd: false,
				modeStart: 'date',
				mode: 'date',
				form: {
					name: '',
					mobile: '',
					Idcard: '',
					showStartTime: '',
					showEndTime: '',
					license_type: '',
				},
				license_isShow: false,
				list: [
					// {
					// 	value: '1',
					// 	label: 'A1驾驶证'
					// },
					// {
					// 	value: '2',
					// 	label: 'A2驾驶证'
					// },
					// {
					// 	value: '3',
					// 	label: 'A3驾驶证'
					// },
					// {
					// 	value: '4',
					// 	label: 'B1驾驶证'
					// },
					// {
					// 	value: '5',
					// 	label: 'B2驾驶证'
					// },
					// {
					// 	value: '6',
					// 	label: 'C1驾驶证'
					// },{
					// 	value: '7',
					// 	label: 'C2驾驶证'
					// },{
					// 	value: '8',
					// 	label: 'C3驾驶证'
					// },{
					// 	value: '9',
					// 	label: 'C4驾驶证'
					// },
					{
						value: '10',
						label: 'D型驾驶证'
					}, {
						value: '11',
						label: 'E型驾驶证'
					}, {
						value: '12',
						label: 'F型驾驶证'
					},
					// {
					// 	value: '13',
					// 	label: 'M型驾驶证'
					// },{
					// 	value: '14',
					// 	label: 'N型驾驶证'
					// },{
					// 	value: '15',
					// 	label: ' P型驾驶证'
					// },
				],
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
					Idcard: [{
							required: true,
							message: '请输入身份号',
							trigger: ['change', 'blur'],
						},
						{
							// 自定义验证函数，见上说明
							validator: (rule, value, callback) => {
								// 上面有说，返回true表示校验通过，返回false表示不通过
								// this.$u.test.mobile()就是返回true或者false的
								return this.$u.test.idCard(value);
							},
							message: '身份证号码不正确',
							// 触发器可以同时用blur和change
							trigger: ['change', 'blur'],
						}
					],
					license_type: [{
						required: true,
						message: '请输入准驾车型',
						// 可以单个或者同时写两个触发验证方式 
						trigger: ['change', 'blur'],
					}],
					showStartTime :[
						{
							required: true,
							message: '请选择驾驶证有效起始日期',
							// 可以单个或者同时写两个触发验证方式 
							trigger: ['change', 'blur'],
						}
					],
					showEndTime:[{
							required: true,
							message: '请选择驾驶证有效终止日期',
							// 可以单个或者同时写两个触发验证方式 
							trigger: ['change', 'blur'],
						},
						]
				}
			};
		},
		onReady() {
			this.$refs.uForm.setRules(this.rules);
		},
		methods: {

			changeStart(e) {
				this.form.showStartTime = e.result
			},
			changeEnd(e) {
				this.form.showEndTime = e.result
			},
			confirm(e) {
				this.form.license_type = e[0].label
			},
			submit() {
				this.$refs.uForm.validate(valid => {
					if (valid) {
						console.log('验证通过');
					} else {
						console.log('验证失败');
					}
				});
				// console.log(this.form)
			}
		},

	}
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
	}

	.content {
		height: 100%;
		padding: 0 30rpx;

		.header {
			height: 88rpx;
			line-height: 88rpx;

			.header_back {
				width: 18rpx;
				height: 36rpx;
			}
		}

		.form_title {
			padding-top: 30rpx;
			color: #3B3B59;
			font-weight: 700;
			font-size: 44rpx;
		}

		.driverTime {
			width: 100%;
			display: flex;
			justify-content: space-between;

			span {
				padding: 0 20rpx;
			}

			.dirverTime_title {
				color: rgb(192, 196, 204);
			}
		}

	}
</style>
