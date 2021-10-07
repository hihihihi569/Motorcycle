<template>
	<view class="content">
		<div class="back">
			<div>
				<navigator url="../../pages/discover/index" hover-class="navigator-hover">
					<image src="../../static/tab/back.png" mode="" class="header_back"
						style="width: 17rpx;height: 30rpx;">
					</image>
				</navigator>
			</div>
			<div style="display: flex;" >
				<span @click="enjor()">					
					<image src="../../static/home/enjor.png" mode="" class="header_back"
						style="width: 30rpx;height: 30rpx;padding: 0 30rpx;">
					</image>
				</span>
				<span @click="report()">...</span>
			</div>
		</div>
		<div class="header">
			【豪车出租】新大洲本田 CM300
		</div>
		<view class="artcle_title">
			<span>
				<image src="../../static/missing-face.png" mode="aspectFit" style="width: 75rpx;height: 75rpx;"></image>
			</span>
			<div>
				<p>139****1114</p>
				<p style="color: #89899B;font-size: 20rpx;">5天前</p>
			</div>
		</view>
		<view class="artcle_body">
			<p>
				本车配置为最高端，铂金顶配版裸车价值56.31万， 动力407马力，单杠四冲程，整车质量170KG，排 量286CC。
			</p>
			<div>
				<image src="../../pages/static/mine/idcard/港澳身份证.png" mode="scaleToFill" style="width: 690rpx;"></image>
			</div>
		</view>
		<comment />
			<u-popup  v-model="show" mode="bottom" length="15%">
					<view class="report" @click="reportBtn()" style="border-bottom: 10rpx solid #f5f5f5;color: #0072FF;height: 50%;">举报</view>
					<view class="report" @click="cancle()">取消</view>
			</u-popup>
	</view>
</template>

<script>
	import comment from './comment.vue';
	import uniShare from '@/uni_modules/uni-share/js_sdk/uni-share.js';
	export default {
		data() {
			return {
				form: {
					title: '',
					intro: '',
				},
				show:false
			}
		},
		components: {
			comment
		},
		methods: {
			reportBtn(){
				uni.navigateTo({
					url:"../Concerning/Reporting_center",
						success:()=>{
							console.log('定向成功')
						},
						fail:()=>{
							console.log('定向失败')
						}}
				)
			},
			report (){
				this.show=true
			},
			cancle () {
				this.show=false
			},
			enjor() {
				uniShare({
					content: { //公共的分享参数配置  类型（type）、链接（herf）、标题（title）、summary（描述）、imageUrl（缩略图）
						type: 0,
						href: 'https://uniapp.dcloud.io/',
						title: '分享至',
						summary: '描述',
						imageUrl: 'https://img-cdn-aliyun.dcloud.net.cn/stream/icon/__UNI__HelloUniApp.png'
					},
					menus: [{
							"img": "/static/app-plus/sharemenu/wechatfriend.png",
							"text": "微信好友",
							"share": { //当前项的分享参数配置。可覆盖公共的配置如下：分享到微信小程序，配置了type=5
								"provider": "weixin",
								"scene": "WXSceneSession"
							}
						},
						{
							"img": "/static/app-plus/sharemenu/wechatmoments.png",
							"text": "微信朋友圈",
							"share": {
								"provider": "weixin",
								"scene": "WXSenceTimeline"
							}
						},
						{
							"img": "/static/app-plus/sharemenu/mp_weixin.png",
							"text": "微信小程序",
							"share": {
								provider: "weixin",
								scene: "WXSceneSession",
								type: 5,
								miniProgram: {
									id: '123',
									path: '/pages/list/detail',
									webUrl: '/#/pages/list/detail',
									type: 0
								},
							}
						},
						{
							"img": "/static/app-plus/sharemenu/weibo.png",
							"text": "微博",
							"share": {
								"provider": "sinaweibo"
							}
						},
						{
							"img": "/static/app-plus/sharemenu/qq.png",
							"text": "QQ",
							"share": {
								"provider": "qq"
							}
						},
						{
							"img": "/static/app-plus/sharemenu/copyurl.png",
							"text": "复制",
							"share": "copyurl"
						},
						{
							"img": "/static/app-plus/sharemenu/more.png",
							"text": "更多",
							"share": "shareSystem"
						}
					],
					cancelText: "取消分享",
				}, e => { //callback
					console.log(e);
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	page {
		height: 100%;
	}

	.content {
		background-color: #F5F5F5;
		position: relative;

		.back {
			height: 88rpx;
			line-height: 88rpx;
			text-align: center;
			font-size: 36rpx;
			position: relative;
			background-color: #fff;

			display: flex;
			justify-content: space-between;
			padding: 0 30rpx;

			.header_back {
				width: 18rpx;
				height: 36rpx;
			}
		}

		.header {
			color: #3B3B59;
			font-size: 37rpx;
			font-weight: 600;
			padding-bottom: 30rpx;
			background-color: #FFFFFF;
		}

		.artcle_title {
			display: flex;
			justify-content: flex-start;
			padding: 0 30rpx;
			background-color: #fff;

			span {
				margin-right: 20rpx;
			}

			p {
				color: #3C3C5A;
				font-size: 25rpx;
			}
		}

		.artcle_body {
			padding: 30rpx;
			font-size: 30rpx;
			color: #3B3B59;
			background-color: #FFFFFF;

			p {
				padding: 20rpx 0;
			}
		}
		.report {
			width: 100%;
			text-align: center;
			height: 45%;
			line-height: 100rpx;
			background-color: #fff;
		}
		
	}
 
</style>
