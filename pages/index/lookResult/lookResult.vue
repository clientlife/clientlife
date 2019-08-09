<template>
	<view>
		<view class="Nav">
			<view class="NavCh">未完成</view>
			<view class="NavCh">待确认</view>
			<view class="NavCh">已完成</view>
		</view>
		<view class="Nav">
			<view class="NavCh1">50件</view>
			<view class="NavCh1">30件</view>
			<view class="NavCh1">100件</view>
		</view>
		<view class="Btns">确认</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
	.Nav {
		width: 100%;
		height: 106rpx;
		display: flex;
		justify-content: space-between;
	}
	.NavCh {
		width: 33.3%;
		height: 106rpx;
		border-right: 1rpx solid #808080;
		border-bottom: 1rpx solid #808080;
		text-align: center;
		line-height: 106rpx;
		font-size: 30rpx;
	}
	.NavCh1 {
		width: 33.3%;
		height: 106rpx;
		border-right: 1rpx solid #808080;
		border-bottom: 1rpx solid #808080;
		text-align: center;
		line-height: 106rpx;
		font-size: 38rpx;
	}
	.Btns {
		position: fixed;
		bottom: 60rpx;
		left: 50%;
		transform: translateX(-50%);
		font-size: 30rpx;
		width: 450rpx;
		height: 55rpx;
		line-height: 55rpx;
		border: 1rpx solid #808080;
		border-radius: 10rpx;
		text-align: center;
	}
</style>
