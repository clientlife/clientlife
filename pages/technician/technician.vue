<template>
	<view>
		<!-- top导航 -->
		<view class="orderTitle">
			<view :class="showAlls?'orderTitleCh2':'orderTitleCh1'" @click="showAll">
				全部
				<view class="orderLine" v-show="showAlls"></view>
			</view>
			<view :class="showWillWorkings?'orderTitleCh2':'orderTitleCh1'" @click="showWillWorking">
				待处理
				<view class="orderLine" v-show="showWillWorkings"></view>
			</view>
			<view :class="showWorkings?'orderTitleCh2':'orderTitleCh1'" @click="showWorking">
				处理中
				<view class="orderLine" v-show="showWorkings"></view>
			</view>
			<view :class="showBuKuans?'orderTitleCh2':'orderTitleCh1'" @click="showBuKuan">
				补款中
				<view class="orderLine" v-show="showBuKuans"></view>
			</view>
			<view :class="showDones?'orderTitleCh2':'orderTitleCh1'" @click="showDone">
				处理完成
				<view class="orderLine" v-show="showDones"></view>
			</view>
		</view>
		<!-- body信息    全部-->
		<section class="AllBodyMsg" v-show="showAlls">
			<view class="AllBodyMsgCh" v-for="(item,index) in allList" :key="index">
				<view class="AllDanHao_Status">
					<view class="All_DanHao">订单号：{{item.num}}</view>
					<view class="All_Status">{{item.status}}</view>
				</view>
				<view class="All_GotoKuTime">入库时间:  {{item.time}}</view>
				<view class="AllBodyShowMsgs">
					<view class="AllShowUser">联系人: {{item.callUser}}</view>
					<view class="AllAddress">{{item.address}}</view>
					<view class="AllTech_Address">{{item.cUserAddress}}</view>
					<view class="AllUser_Address_Imgs">
						<image src="../../static/images/lat.png" mode=""></image>
						<view class="AllUser_Address">{{item.userAddress}}</view>
					</view>
					<view class="AllUser_Tel_Imgs">
						<image src="../../static/images/tel.png" mode=""></image>
						<view class="AllUser_Tel">{{item.userPhone}}</view>
					</view>
				</view>
			</view>
		</section>
		<!-- 待处理 -->
		<section class="AllBodyMsg" v-show="showWillWorkings">
			<view class="AllBodyMsgCh" v-for="(item,index) in willList" :key="index" @click="gotoWaitingDo">
				<view class="AllDanHao_Status">
					<view class="All_DanHao">订单号：{{item.num}}</view>
					<view class="All_Status">{{item.status}}</view>
				</view>
				<view class="All_GotoKuTime">入库时间:  {{item.time}}</view>
				<view class="AllBodyShowMsgs">
					<view class="AllShowUser">联系人: {{item.callUser}}</view>
					<view class="AllAddress">{{item.address}}</view>
					<view class="AllTech_Address">{{item.cUserAddress}}</view>
					<view class="AllUser_Address_Imgs">
						<image src="../../static/images/lat.png" mode=""></image>
						<view class="AllUser_Address">{{item.userAddress}}</view>
					</view>
					<view class="AllUser_Tel_Imgs">
						<image src="../../static/images/tel.png" mode=""></image>
						<view class="AllUser_Tel">{{item.userPhone}}</view>
					</view>
				</view>
			</view>
		</section>
		<!-- 处理中 -->
		<section class="AllBodyMsg" v-show="showWorkings">
			<view class="AllBodyMsgCh" v-for="(item,index) in dingList" :key="index" @click="goToworking">
				<view class="AllDanHao_Status">
					<view class="All_DanHao">订单号：{{item.num}}</view>
					<view class="All_Status">{{item.status}}</view>
				</view>
				<view class="All_GotoKuTime">入库时间:  {{item.time}}</view>
				<view class="AllBodyShowMsgs">
					<view class="AllShowUser">联系人: {{item.callUser}}</view>
					<view class="AllAddress">{{item.address}}</view>
					<view class="AllTech_Address">{{item.cUserAddress}}</view>
					<view class="AllUser_Address_Imgs">
						<image src="../../static/images/lat.png" mode=""></image>
						<view class="AllUser_Address">{{item.userAddress}}</view>
					</view>
					<view class="AllUser_Tel_Imgs">
						<image src="../../static/images/tel.png" mode=""></image>
						<view class="AllUser_Tel">{{item.userPhone}}</view>
					</view>
				</view>
			</view>
		</section>
		<!-- 补款中 -->
		<section class="AllBodyMsg" v-show="showBuKuans">
			<view class="AllBodyMsgCh" v-for="(item,index) in bukuanList" :key="index" @click="goTofillMoney">
				<view class="AllDanHao_Status">
					<view class="All_DanHao">订单号：{{item.num}}</view>
					<view class="All_Status">{{item.status}}</view>
				</view>
				<view class="All_GotoKuTime">入库时间:  {{item.time}}</view>
				<view class="AllBodyShowMsgs">
					<view class="AllShowUser">联系人: {{item.callUser}}</view>
					<view class="AllAddress">{{item.address}}</view>
					<view class="AllTech_Address">{{item.cUserAddress}}</view>
					<view class="AllUser_Address_Imgs">
						<image src="../../static/images/lat.png" mode=""></image>
						<view class="AllUser_Address">{{item.userAddress}}</view>
					</view>
					<view class="AllUser_Tel_Imgs">
						<image src="../../static/images/tel.png" mode=""></image>
						<view class="AllUser_Tel">{{item.userPhone}}</view>
					</view>
				</view>
			</view>
		</section>
		<!-- 处理完成 -->
		<section class="AllBodyMsg" v-show="showDones">
			<view class="AllBodyMsgCh" v-for="(item,index) in doneList" :key="index" @click="goToDone">
				<view class="AllDanHao_Status">
					<view class="All_DanHao">订单号：{{item.num}}</view>
					<view class="All_Status">{{item.status}}</view>
				</view>
				<view class="All_GotoKuTime">入库时间:  {{item.time}}</view>
				<view class="AllBodyShowMsgs">
					<view class="AllShowUser">联系人: {{item.callUser}}</view>
					<view class="AllAddress">{{item.address}}</view>
					<view class="AllTech_Address">{{item.cUserAddress}}</view>
					<view class="AllUser_Address_Imgs">
						<image src="../../static/images/lat.png" mode=""></image>
						<view class="AllUser_Address">{{item.userAddress}}</view>
					</view>
					<view class="AllUser_Tel_Imgs">
						<image src="../../static/images/tel.png" mode=""></image>
						<view class="AllUser_Tel">{{item.userPhone}}</view>
					</view>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				showAlls: true, //全部订单显示
				showWillWorkings: false, //待处理
				showWorkings: false, //处理中
				showBuKuans: false, //补款中
				showDones:false,  //处理完成
				allList:[{
					num:'xssf4324789713',
					status:'处理中',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				},{
					num:'xssf4324789713',
					status:'待处理',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				},{
					num:'xssf4324789713',
					status:'处理中',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				},{
					num:'xssf4324789713',
					status:'待处理',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				}],
				// 待处理
				willList:[{
					num:'xssf4324789713',
					status:'待处理',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				}],
				// 处理中
				dingList:[{
					num:'xssf4324789713',
					status:'处理中',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				}],
				// 补款中
				bukuanList:[{
					num:'xssf4324789713',
					status:'补款中',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				}],
				// 处理完成
				doneList:[{
					num:'xssf4324789713',
					status:'处理完成',
					time:'今天  17：45',
					callUser:'曾浩',
					address:'翡翠城店',
					cUserAddress:'四川省成都市武侯区桂溪街道天府大道中段',
					userAddress:'666号希顿国际C座1408',
					userPhone:'1356498745',
					id:1
				}]
			}
		},
		methods: {
			showAll() {
				this.showAlls = true
				this.showWillWorkings = false
				this.showWorkings = false
				this.showBuKuans = false
				this.showDones = false
			},
			showWillWorking() {
				this.showAlls = false
				this.showWillWorkings = true
				this.showWorkings = false
				this.showBuKuans = false
				this.showDones = false
			},
			showWorking() {
				this.showAlls = false
				this.showWillWorkings = false
				this.showWorkings = true
				this.showBuKuans = false
				this.showDones = false
			},
			showBuKuan() {
				this.showAlls = false
				this.showWillWorkings = false
				this.showWorkings = false
				this.showBuKuans = true
				this.showDones = false
			},
			showDone() {
				this.showAlls = false
				this.showWillWorkings = false
				this.showWorkings = false
				this.showBuKuans = false
				this.showDones = true
			},
			// 跳转待处理
			gotoWaitingDo() {
				uni.navigateTo({
					url:'waitingDo/waitingDo'
				})
			},
			// 跳转处理中
			goToworking() {
				uni.navigateTo({
					url:'working/working'
				})
			},
			// 跳转补款中
			goTofillMoney() {
				uni.navigateTo({
					url:'fillMoney/fillMoney'
				})
			},
			// 跳转处理完成
			goToDone() {
				uni.navigateTo({
					url:'done/done'
				})
			}
		}
	}
</script>

<style>
	.orderTitle {
		z-index: 50;
		position: fixed;
		top: 0rpx;
		left: 0rpx;
		width: 100%;
		height: 104rpx;
		background-color: #F2F2F2;
		display: flex;
		justify-content: space-between;
	}
	
	.orderTitleCh1 {
		z-index: 40;
		position: relative;
		width: 25%;
		height: 106rpx;
		line-height: 106rpx;
		text-align: center;
		font-size: 32rpx;
		color: black;
		/* margin-top: 56px; */
		/* font-weight: bold; */
	}
	.orderTitleCh2 {
		z-index: 40;
		position: relative;
		width: 25%;
		height: 106rpx;
		line-height: 106rpx;
		text-align: center;
		font-size: 32rpx;
		color: rgb(231, 103, 29);
	}
	.orderLine {
		position: absolute;
		width: 50%;
		left: 25%;	
		height: 8rpx;
		background: rgb(231, 103, 29);
		bottom: 14rpx;
	/* 	display: none;
		animation-fill-mode: forwards; */
	}
	/* body信息   全部 */
	.AllBodyMsg {
		width: 100%;
		height: 100%;
		overflow: scroll;
		margin-top: 95rpx;
	}
	.AllBodyMsgCh {
		width: 100%;
		height: 340rpx;
		margin-top: 10rpx;
		border-top: 1rpx solid #808080;
		border-bottom: 1rpx solid #808080;
	}
	.AllDanHao_Status {
		width: 100%;
		height: 58rpx;
		border-bottom: 1rpx solid #808080;
		display: flex;
		justify-content: space-between;
	}
	.All_DanHao {
		width: 400rpx;
		height: 58rpx;
		line-height: 58rpx;
		margin-left: 2%;
		font-size: 26rpx;
	}
	.All_Status {
		width: 200rpx;
		height: 58rpx;
		margin-right: 2%;
		line-height: 58rpx;
		text-align: right;
		font-size: 26rpx;
		color: rgb(2, 95, 59);
	}
	.All_GotoKuTime {
		width: 96%;
		margin-left: 2%;
		font-size: 26rpx;
		height: 58rpx;
		line-height: 58rpx;
	}
	.AllBodyShowMsgs {
		position: relative;
		width: 100%;
		height: 220rpx;
		border-top: 1rpx solid #808080;
	}
	.AllShowUser {
		position: absolute;
		top: 5rpx;
		left: 2%;
		width: 300rpx;
		height: 40rpx;
		line-height: 40rpx;
		font-size: 30rpx;
	}
	.AllAddress {
		position: absolute;
		top: 5rpx;
		right: 2%;
		font-size: 26rpx;
		text-align: right;
	}
	.AllTech_Address {
		position: absolute;
		left: 50%;
		top: 47rpx;
		transform: translateX(-50%);
		width: 600rpx;
		height: 60rpx;
		font-size: 30rpx;
		line-height: 60rpx;
		text-align: center;
	}
	.AllUser_Address_Imgs {
		position: absolute;
		left: 2%;
		top: 100rpx;
		width: 96%;
		height: 60rpx;
	}
	.AllUser_Address_Imgs image,.AllUser_Tel_Imgs image {
		position: absolute;
		top: 10rpx;
		width: 40rpx;
		height: 40rpx;
		
	}
	.AllUser_Address,.AllUser_Tel {
		position: absolute;
		top:0rpx;
		left: 60rpx;
		font-size: 26rpx;
		height: 60rpx;
		line-height: 60rpx;
	}
	.AllUser_Tel_Imgs {
		position: absolute;
		top: 157rpx;
		left: 2%;
		width: 96%;
	}
	
</style>
