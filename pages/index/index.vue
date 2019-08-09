<template>
	<view class="tall">
		<view class="Top">
			<view class="TopHeadImgs">
				<open-data type="userAvatarUrl"></open-data>
			</view>
			<view class="clientMsgs">
				<open-data type="userNickName" class="nickName"></open-data>
				<view class="logo">生活管家</view>
				<view class="status">在店</view>
				<view class="phone">13350057828</view>
			</view>
		</view>
		<!-- body -->
		<view class="BodyMsgs">
			<view class="BodyTop">
				<view class="BodyTopName">需取件</view>
				<view class="BodyTopName">需确认完成</view>
				<view class="BodyTopName">等待却仍时间</view>
				<view class="BodyTopName">需送件</view>
			</view>
			<view class="BodySecond">
				<view class="BodyTopName">100件</view>
				<view class="BodyTopName">50件</view>
				<view class="BodyTopName">30件</view> 
				<view class="BodyTopName">100件</view>
			</view>
		</view>
		<!-- 跳转其它信息 -->
		<view class="goToOthers">
			<view class="othersName">切换身份</view>
			<image src="../../static/images/jiantou.png" mode=""  @click="exchange"></image>
		</view>
		<view class="goToOthers">
			<view class="othersName">业绩查询</view>
			<image src="../../static/images/jiantou.png" @click="lookResult" mode=""></image>
		</view>
		<!-- 推出登录按钮 -->
		<view class="Btns">退出登录</view>
		<!-- 浮标 -->
		<view class="DingDan" @click="goToDingDan">订单</view>
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

		},
		methods: {
			// 切换身份
			exchange() {
				uni.navigateTo({
					url:'exchangeIdentity/exchangeIdentity'
				})
			},
			// 业绩查询
			lookResult() {
				uni.navigateTo({
					url:'lookResult/lookResult'
				})
			},
			// 进入订单
			goToDingDan() {
				uni.navigateTo({
					url:'../technician/technician'
				})
			}
		}
	}
</script>

<style>
	.tall {
		width: 100%;
		height: 100%;
	}
	.Top {
		width: 100%;
		height: 280rpx;
		background-color: black;
		position: relative;
	}
	.TopHeadImgs {
		position: absolute;
		top:50rpx;
		left: 30rpx;
		width: 160rpx;
		height: 160rpx;
		border-radius: 50%;
		overflow: hidden;
	}
	.clientMsgs {
		position: absolute;
		top: 65rpx;
		left: 210rpx;
		width: 300rpx;
		height: 200rpx;
	}
	.nickName {
		width: 70rpx;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 30rpx;
		color: white;
	}
	.logo {
		position: absolute;
		top: 70rpx;
		left: 0rpx;
		width: 150rpx;
		height: 40rpx;
		line-height: 40rpx;
		color: white;
		font-size: 30rpx;
	}
	.status {
		position: absolute;
		left: 67rpx;
		top: 10rpx;
		font-size: 24rpx;
		width: 100rpx;
		text-align: center;
		line-height: 40rpx;
		height: 40rpx;
		background-color: white;
		color: black;
		border-radius: 12rpx;
	}
	.phone {
		position: absolute;
		top: 122rpx;
		width: 300rpx;
		height: 40rpx;
		color: white;
		line-height: 40rpx;
		font-size: 30rpx;
	}
	.BodyMsgs {
		width: 100%;
		height: 236rpx;
	}
	.BodyTop,.BodySecond {
		width: 100%;
		height: 100rpx;
		display: flex;
		justify-content: space-between;
		
	}
	.BodyTopName {
		width: 25%;
		height: 100rpx;
		border-right: 1rpx solid #999999;
		border-bottom: 1rpx solid #999999;
		text-align: center;
		line-height: 100rpx;
		font-size: 30rpx;
	}
	/* 跳转 */
	.goToOthers {
		width: 100%;
		height: 70rpx;
		position: relative;
		margin-top: 10rpx;
		border-top: 1rpx solid #999999;
		border-bottom: 1rpx solid #999999;
	}
	.othersName {
		position: absolute;
		width: 150rpx;
		height: 40rpx;
		line-height: 40rpx;
		left: 2%;
		top: 15rpx;
		font-size: 24rpx;
	}
	.goToOthers image {
		position: absolute;
		width: 30rpx;
		height: 30rpx;
		right: 2%;
		top: 20rpx;
	}
	.Btns {
		position: fixed;
		bottom: 280rpx;
		left: 50%;
		transform: translateX(-50%);
		width: 400rpx;
		height: 60rpx;
		border-radius: 10rpx;
		border: 1rpx solid #C0C0C0;
		text-align: center;
		line-height: 60rpx;
		font-size: 28rpx;
		
	}
	.DingDan {
		position: fixed;
		bottom: 60rpx;
		width: 126rpx;
		height: 126rpx;
		background-color: rgb(2, 95, 59);
		text-align: center;
		line-height: 126rpx;
		font-size: 26rpx;
		color: black;
		border-radius: 50%;
		right: 2%;
	}
</style>
