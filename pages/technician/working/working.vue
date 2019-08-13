<template>
	<view>
		<view class="TopStatus">当前状态:处理中</view>
		<view class="TopTime">开始处理:今天 17：00-18：00</view>
		<view class="userMsgs">
			<view class="userName">联系人:曾浩</view>
			<view class="userAddress">四川省成都市武侯区桂系街天府大道中段</view>
			<view class="detailAddress">
				<image src="../../../static/images/lat.png" mode=""></image>
				<view class="address">666号希顿国际C座1408</view>
			</view>
			<view class="userTel">
				<image src="../../../static/images/tel.png" mode=""></image>
				<view class="Tel">13350058238</view>
			</view>
		</view>
		<view class="goodsMsgs">
			<view class="dingdanNum">订单号:xxxxxxxxxxx</view>
			<view class="dingdanTime">下单时间:xxxxxxx</view>
			<view class="goodsCount">商品:x件</view>
			<view class="Goods">
				<view class="GoodsTitle">
					<view class="GoodsTitleCh1">品类</view>
					<view class="GoodsTitleCh2">种类</view>
					<view class="GoodsTitleCh1">数量</view>
				</view>
				<view class="GoodsAbout">
					<view class="GoodsAboutCh1">衣物清洁</view>
					<view class="GoodsAboutCh2">
						衣物清洁衣
						<br />
						物清洁衣物清洁衣物清洁</view>
					<view class="GoodsAboutCh1">x1</view>
					
				</view>
				<view class="GoodsAbout">
					<view class="GoodsAboutCh1">衣物清洁</view>
					<view class="GoodsAboutCh2">
						衣物清洁衣
						<br />
						物清洁衣物清洁衣物清洁</view>
					<view class="GoodsAboutCh1">x1</view>
					
				</view>
				<view class="GoodsAbout">
					<view class="GoodsAboutCh1">衣物清洁</view>
					<view class="GoodsAboutCh2">
						衣物清洁衣
						<br />
						物清洁衣物清洁衣物清洁</view>
					<view class="GoodsAboutCh1">x1</view>
					
				</view>
			</view>
		</view>
		<view class="keHuBeiZhu">客户备注:xxxxxxxx</view>
		<!-- <view class="BodyMsg">
			
		</view> -->
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
	.TopStatus,
	.TopTime {
		width: 100%;
		height: 70rpx;
		line-height: 70rpx;
		font-size: 30rpx;
		border-bottom: 1rpx solid #C0C0C0;
	}

	.userMsgs {
		width: 100%;
		height: 210rpx;
		border-bottom: 1rpx solid #C0C0C0;
	}

	.userName {
		width: 96%;
		margin-left: 2%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 30rpx;
	}

	.userAddress {
		width: 100%;
		height: 60rpx;
		line-height: 60rpx;
		text-align: center;
		font-size: 30rpx;
	}

	.detailAddress,
	.userTel {
		position: relative;
		width: 100%;
		height: 60rpx;
	}

	.detailAddress image,
	.userTel image {
		position: absolute;
		top: 10rpx;
		height: 40rpx;
		width: 40rpx;
		left: 2%;
	}

	.address,
	.Tel {
		position: absolute;
		font-size: 24rpx;
		height: 60rpx;
		line-height: 60rpx;
		top: 0rpx;
		left: 70rpx;
	}

	.goodsMsgs {
		width: 100%;
		min-height: 400rpx;
		border: 1rpx solid #C0C0C0;
	}

	.dingdanNum,
	.dingdanTime {
		width: 96%;
		margin-left: 2%;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 24rpx;
	}

	.goodsCount {
		width: 96%;
		height: 60rpx;
		line-height: 60rpx;
		margin-left: 2%;
		font-size: 24rpx;
	}

	.GoodsTitle {
		width: 100%;
		height: 40rpx;
		display: flex;
		justify-content: space-between;
	}

	.GoodsTitleCh1 {
		width: 20%;
		height: 40rpx;
		line-height: 40rpx;
		text-align: center;
		font-size: 24rpx;
	}

	.GoodsTitleCh2 {
		width: 40%;
		height: 40rpx;
		line-height: 40rpx;
		text-align: center;
		font-size: 24rpx;
	}

	.GoodsAbout {
		width: 100%;
		height: 65rpx;
		display: flex;
		justify-content: space-between;
	}

	.GoodsAboutCh1 {
		width: 20%;
		height: 65rpx;
		line-height: 65rpx;
		text-align: center;
		font-size: 24rpx;

	}

	.GoodsAboutCh2 {
		width: 40%;
		height: 65rpx;
		// line-height: 65rpx;/
		text-align: center;
		font-size: 24rpx;

	}

	.keHuBeiZhu {
		width: 96%;
		margin-left: 2%;
		font-size: 24rpx;
		line-height: 60rpx;
		height: 60rpx;
	}

	
</style>
