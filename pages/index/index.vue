<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
			<text class="title">{{text}}</text>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				text:'就是玩儿'
			}
		},
		onLoad() {
		uni.setStorageSync('name','就是玩儿')
		setTimeout(()=>{
			this.getName()
		},1000)
		},
		methods: {
			getName(){
				let name = uni.getStorageSync('name')
				console.log('取出name',name);
			},
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
		flex-direction: column;
		align-items: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
