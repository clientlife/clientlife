<template>
	<view>
		<view class="TopStatus">当前状态:待处理</view>
		<view class="TopTime">入库时间:今天 17：00-18：00</view>
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
					<view class="GoodsTitleCh1">选择</view>
				</view>
				<view class="GoodsAbout">
					<view class="GoodsAboutCh1">衣物清洁</view>
					<view class="GoodsAboutCh2">
						衣物清洁衣
						<br />
						物清洁衣物清洁衣物清洁</view>
					<view class="GoodsAboutCh1">x1</view>
					<view class="GoodsAboutCh1">
						<label class="checkbox">
							<checkbox value="" />
						</label>
					</view>
				</view>
				<view class="GoodsAbout">
					<view class="GoodsAboutCh1">衣物清洁</view>
					<view class="GoodsAboutCh2">
						衣物清洁衣
						<br />
						物清洁衣物清洁衣物清洁</view>
					<view class="GoodsAboutCh1">x1</view>
					<view class="GoodsAboutCh1">
						<label class="checkbox">
							<checkbox value="" />
						</label>
					</view>
				</view>
				<view class="GoodsAbout">
					<view class="GoodsAboutCh1">衣物清洁</view>
					<view class="GoodsAboutCh2">
						衣物清洁衣
						<br />
						物清洁衣物清洁衣物清洁</view>
					<view class="GoodsAboutCh1">x1</view>
					<view class="GoodsAboutCh1">
						<label class="checkbox">
							<checkbox value="" />
						</label>
					</view>
				</view>
			</view>
		</view>
		<view class="keHuBeiZhu">客户备注:xxxxxxxx</view>
		<!-- <view class="BodyMsg">
			
		</view> -->
		<view class="Btns">
			<view class="BtnsLeft" @click="buKuan">补款</view>
			<view class="BtnsRight" @click="working">开始处理</view>
		</view>
		<!-- 补款弹窗 -->
		<view class="mengBan" v-show="showBK"></view>
		<view class="buKuan" v-show="showBK">
			<view class="buKuanTitel">补款确认</view>
			<view class="buKuanPrice">
				<view class="buKuanPriceName">补款金额</view>
				<input type="number" value="" />
				<text>元</text>
			</view>
			<view class="buKuanbeiZhu">
				<view class="buKuanBeiZhuName">补款备注</view>
				<textarea value="" placeholder="补款备注" />
			</view>
			<view class="buKuanBtns" @click="sendMsg">通知客户</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showBK:false,   //弹出补款弹窗
			}
		},
		methods: {
			// 补款
			buKuan() {
				this.showBK = true
			},
			// 通知客户
			sendMsg() {
				this.showBK = false
			},
			// 开始处理
			working() {
				uni.navigateTo({
					url:'working'
				})
			}
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

	.Btns {
		position: fixed;
		bottom: 40rpx;
		width: 70%;
		height: 50rpx;
		left: 15%;
		display: flex;
		justify-content: space-between;
	}

	.BtnsLeft,
	.BtnsRight {
		width: 130rpx;
		height: 50rpx;
		border-radius: 10rpx;
		border: 1rpx solid #C8C7CC;
		color: #F0AD4E;
		font-size: 26rpx;
		text-align: center;
		line-height: 50rpx;
	}
	
	/* 补款弹窗 */
	.mengBan {
		position: fixed;
		top: 0rpx;
		left: 0rpx;
		width: 100%;
		height: 100%;
		background: rgba(1,1,1,0.6);
		z-index: 10;
	}
	.buKuan {
		position: fixed;
		z-index: 30;
		width: 560rpx;
		height: 400rpx;
		left: 84rpx;
		top: 340rpx;
		background: white;
		
	}
	.buKuanTitel {
		width: 100%;
		height: 50rpx;
		line-height: 50rpx;
		font-size: 28rpx;
		text-align: center;
	}
	.buKuanPrice {
		position: relative;
		width: 400rpx;
		height: 60rpx;
		margin-left: 80rpx;
		margin-top: 20rpx;
		font-size: 28rpx;
	}
	.buKuanPriceName {
		position: absolute;
		width: 120rpx;
		font-size: 28rpx;
		height: 60rpx;
		line-height: 60rpx;
		top: 0rpx;
		left: 0rpx;
	}
	.buKuanPrice input {
		position: absolute;
		top: 0rpx;
		left: 133rpx;
		height: 40rpx;
		width: 192rpx;
		border: 1rpx solid #C0C0C0;
		font-size: 28rpx;
	}
	.buKuanPrice text {
		position: absolute;
		top: 0rpx;
		height: 60rpx;
		line-height: 60rpx;
		left: 340rpx;
		
	}
	.buKuanbeiZhu {
		position: relative;
		margin-top: 20rpx;
		width: 402rpx;
		margin-left: 80rpx;
		height: 175rpx;
	}
	.buKuanBeiZhuName {
		position: absolute;
		top: 0rpx;
		left: 0rpx;
		width: 120rpx;
		height: 60rpx;
		/* line-height: 60rpx; */
		font-size: 28rpx;
	}
	.buKuanbeiZhu textarea {
		position: absolute;
		top: 0rpx;
		left: 134rpx;
		width: 283rpx;
		font-size: 28rpx;
		height: 175rpx;
		border: 1rpx solid #C0C0C0;
	}
	.buKuanBtns {
		margin-top: 18rpx;
		width: 130rpx;
		height: 50rpx;
		border: 1rpx solid #C0C0C0;
		font-size: 28rpx;
		line-height: 50rpx;
		text-align: center;
		margin-left: 215rpx;
	}
</style>
