<template>
	<view class="">
		<view class="">
			数据的学习
		</view>
		<view class="">
			{{msg}}
		</view>
		<view class="" v-for="(item,index) in arr" :key='item.id'>
	序号：{{index}}	名字：{{item.name}} ,年龄：{{item.age}}
		</view>
		<button type="default" v-on:click="clickHandle(20,$event)">anniu
		</button>
	</view>
</template>

<script>
	export default{
		data(){
			return {
				msg:"hello",
				arr:[
					{
						name:'wu',
						age:15,
						id:4
					},
					{
						name:'qq',
						age:13,
						id:42
					},
					{
						name:'wq',
						age:12,
						id:41
					},
					{
						name:'ccc',
						age:5,
						id:43
					}
				]
			}
		},
		methods:{
			clickHandle(num,e){
				console.log("nihao",num,e)
			}
		}
	}
</script>

<style>
</style>
