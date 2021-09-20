<template>
	<view class="">
		<view class="">
			导航跳转
		</view>
		<navigator url="/pages/detail/detail">跳转至详情页</navigator>
		<navigator url="/pages/message/message" open-type="switchTab">跳转至信息页</navigator>
		<navigator url="/pages/detail/detail" open-type="redirect">跳转至详情页</navigator>
		<button type="default" @click="goDetail">跳转至详情页</button>
			<button type="default" @click="goMessage">跳转至信息页</button>
			<button type="default" @click="redirectDetail">跳转至详细页并关闭当前页面</button>
	</view>
</template>

<script>
	export default{
		onLoad() {
			console.log('导航页面卸载了')
		},
		methods:{
			goDetail(){
				uni.navigateTo({
					url:'/pages/detail/detail'
				})
			},
			goMessage(){
				uni.switchTab({
					url:'../message/message'
				})
			},
			redirectDetail(){
				uni.redirectTo({
					url:'/pages/detail/detail'
				})
			}
			
		}
	}
</script>

<style>
</style>
