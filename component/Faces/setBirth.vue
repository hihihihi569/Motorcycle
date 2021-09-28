<template>
	<view class="content">
		<div class="back">
			<navigator url="./face" hover-class="navigator-hover" style="display: inline-block; float: left;">
				<image src="../../static/tab/back.png" mode="" class="header_back" style="width: 17rpx;height: 30rpx;">
				</image>
			</navigator>
			<span>设置生日</span>
		</div>
		<div class="nick_items">
			<u-form :model="form" ref="uForm">
				<u-form-item prop="name" label="生日" label-width="240rpx" style="color: #89899B;">
					<view class="uni-list" style="width: 100%; text-align: right;">
						<view class="uni-list-cell">			
							<view class="uni-list-cell-db">
								<picker mode="date" :value="date" :start="startDate" :end="endDate" @change="bindDateChange">
									<view class="uni-input">
									<span> {{date}}</span>
									<p>
										<image src="../../static/preference/preference/next.png" mode="aspectFit"
											style="width: 27rpx;height: 27rpx; vertical-align: inherit;padding-left: 20rpx;">
										</image>
									</p>
									</view>
								</picker>
							</view>							
						</view>
					</view>
					
				</u-form-item>
			</u-form>
			<view class="uni-picker-tips">
				注：选择当前时间之前70年的时间, 不在区间内不能选中
			</view>
		</div>

		
	</view>
</template>

<script>
	export default {
		data() {
			const currentDate = this.getDate({
				format: true
			})
			return {
				form: {
					userbirth: ''
				},
				date: currentDate,
				show: false,
			}
		},
		computed: {
			startDate() {
				return this.getDate('start');
			},
			endDate() {
				return this.getDate('end');
			}
		},
		methods: {
			change(e) {
				console.log('提交', e)
				console.log('endYear', this.endYear)
			},
			open() {
				this.show = true
			},
			bindDateChange: function(e) {
				
            console.log('picker发送选择改变，携带值为', e)
				this.date = e.detail.value
			},
			getDate(type) {
				const date = new Date();
				let year = date.getFullYear();
				let month = date.getMonth() + 1;
				let day = date.getDate();

				if (type === 'start') {
					year = year - 60;
				} else if (type === 'end') {
					year = year ;
				}
				month = month > 9 ? month : '0' + month;
				day = day > 9 ? day : '0' + day;
				return `${year}-${month}-${day}`;
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
			margin: 20rpx 0;
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
		.uni-picker-tips {
			font-size: 24rpx;
			text-align: center;
			color: red;
		}
		.uni-input {
			
			    display: flex;
			    justify-content: flex-end;
				font-size: 28rpx;
		}
	}
	.u-form-item--right__content__slot[data-v-5e7216f1] {
		width: 100% !important;
		text-align: right !important;
	}
</style>
