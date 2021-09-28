<template>
	<view>
		<top></top>
		<warmService></warmService>
		<commonTool></commonTool>
		<tabBar :pagePath="'/pages/PersonCore/index'"></tabBar>
	</view>
</template>

<script>
	import top from './top.vue'
	import warmService from './warmService.vue'
	import commonTool  from './commonTool'
	export default{
		data(){
			return {}
		},
		components:{
			top,
			warmService,
			commonTool
		},
		methods:{
			ceshi:()=>{
				uni.navigateTo({
				    url: '/component/top'
				});
			}
		}
	}
</script>

<style>
</style>
