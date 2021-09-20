<template>
	<view class="">
		<button type="default" @click="get">发送get请求</button>
		<button type="default" @click="setStorage">存储数据</button>
		<button type="default" @click="getStorage">获取数据</button>
		<button type="default" @click="removeId">移除数据</button>
		<view class="">
			列表
		</view>
		<view class="box.item" v-for="item in list">
			{{item}}
		</view>
	<!-- 	<button type="default" @click="pullDown">
			下拉刷新
		</button> -->
	</view>
</template>

<script>
	export default{
		data(){
			return {
				list:['前端','java','大数据','前端12','java33','大数据4','前端44','java4443','大数3据']
			}
		},
		onPullDownRefresh() {
			console.log('触发了下拉刷新');
		
			setTimeout(()=>{
					this.list=['前端','java','ui','大数据'];
					uni.stopPullDownRefresh()
			},2000)
			
		},
		onReachBottom() {
			console.log('到底'),
			this.list=[...this.list,...['DAA','JAJAAJA']]
		},
		methods:{
			pullDown(){
				uni.startPullDownRefresh()
			},
			get(){
				uni.request({
					url:'https://api-hmugo-web.itheima.net/api/public/v1/home/swiperdata',
					success(res){
						console.log(res)
					}
				})
			},
		setStorage(){
			// uni.setStorage({
			// 	key:'id',
			// 	data:70,
			// 	success(){
			// 		console.log('存储成功')
			// 	}
			// })
			uni.setStorageSync('id',100)
		},
		getStorage(){
			uni.getStorage({
				key:'id',
				success(res){
					console.log('获取成功',res.data)
				}
			})
			
		},
		removeId(){
			uni.removeStorage({
				key:'id',
				success(){
					console.log('删除成功')
				}
			})
		}
		}
	}
</script>

<style>
	.box.item{
		height: 100px;
		line-height: 100px;
	}
</style>
