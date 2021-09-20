<template>
	<view class="">
	<button type="default" @click="chooseImg">上传图片</button>
	<image :src="item" mode="" v-for="item in imgArr" @click="previewImg(item)"></image>
	<!-- #ifdef H5 -->
	<view class="">
		h5
	</view>
	<!-- #endif -->
	<!-- #ifdef MP-WEIXIN -->
	<view class="">
	小程序
	</view>
		<!-- #endif -->
	</view>
</template>

<script>
	export default{
		data(){
			return{
				imgArr:[]
			}
		},
		methods:{
			chooseImg(){
				uni.chooseImage({
					count:5,
					success:res=> {
						this.imgArr=res.tempFilePaths
					}
				})
			
			},
		previewImg(current){
			uni.previewImage({
				current,
				urls:this.imgArr,
				loop:true,
				indicator:'number'
			})
		},
		onLoad(){
			// #ifdef MP-WEIXIN
			console.log('在微信小程序中打印')
			// #endif
			// #ifdef H5
			console.log('在h5中打印')
			// #endif
		}
		}
	}
</script>

<style>
</style>
