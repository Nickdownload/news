<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
			<button type="default" @click="sendImg"> 上传图片</button>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {
           uniCloud.callFunction({
               name: 'login',
               success(res){
				   console.log(res)
			   },
               fail(){},
               complete(){}
           });
		},
		methods: {
           sendImg(){
			   uni.chooseImage({
				   success(e){
					  console.log(e) 
				   },
				   fail(){
					   
				   },
				   complete(){
					   
				   },
			   })
		   }
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
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
