<template>
	<view class="">
	<!-- 	<view>
			<text>
				唱歌跳舞打篮球
			</text> 
		</view>
		<view>
			<text selectable>
				唱歌跳舞打篮球
			</text> 
		</view>
		<view>
			<text selectable space="emsp">
				唱歌     跳舞打篮球
			</text> 
		</view>
		<view>
			<text>
			&amp;
			</text> 
		</view> -->
		<view class="box" hover-class="activebox" hover-start-time="2000">
			你好
		</view>
		<button type="warn" size="mini" plain="">按钮</button>
		<button loading="">按钮</button>
		<image src="../../static/logo.png" mode="aspectFit"></image>
	</view>
</template>

<script>
</script>

<style>
	.box{
		width: 40px;height: 40px;
		background-color: #007AFF;
		
	}
	.activebox{
		background-color: #4CD964;
	}
	
</style>
