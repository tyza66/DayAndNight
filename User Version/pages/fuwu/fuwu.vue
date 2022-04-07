<template>
	<view>
		<view class="top"></view>
		<view class="all">
			<view class="left">
				<view class="item" @click="r1r()" :id="spe1">
					<image src="../../static/icons/x1.png"></image>
					<p>护工服务</p>
				</view>
				<view class="item" @click="r2r()" :id="spe2">
					<image src="../../static/icons/x2.png" ></image>
					<p>医院咨询</p>
				</view>
				<view class="item" @click="r3r()" :id="spe3">
					<image src="../../static/icons/x3.png"></image>
					<p>更多服务</p>
				</view>
				<view class="item" @click="r4r()" :id="spe4">
					<image src="../../static/icons/x4.png"></image>
					<p>在线商城</p>
				</view>
				<view class="item" @click="r5r()" :id="spe5">
					<image src="../../static/icons/x5.png"></image>
					<p>意见建议</p>
				</view>
			</view>
			<view class="right" v-if="r1">
				<view class="someting">
					<image src="../../static/icons/dan.png"></image>
					<p>短工雇佣</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/anmo.png"></image>
					<p>按摩服务</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/qing.png"></image>
					<p>清理服务</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/xin.png"></image>
					<p>心理辅导</p>
				</view>
			</view>
			<view class="right" v-if="r2">
				<view class="someting">
					<image src="../../static/icons/wen.png"></image>
					<p>在线问诊</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/ziy.png"></image>
					<p>心理咨询</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/hez.png"></image>
					<p>合作医院</p>
				</view>
			</view>
			<view class="right" v-if="r3">
				<view class="someting">
					<image src="../../static/icons/dan.png"></image>
					<p>护工招募</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/dan.png"></image>
					<p>线下推广</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/dan.png"></image>
					<p>会员积分</p>
				</view>
			</view>
			<view class="right" v-if="r4">
				<view class="someting">
					<image src="../../static/icons/yueka.png"></image>
					<p>购买月卡</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/riyong.png"></image>
					<p>买日用品</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/you.png"></image>
					<p>抢优惠券</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/hongbao.png"></image>
					<p>大额红包</p>
				</view>
			</view>
			<view class="right" v-if="r5">
				<view class="someting">
					<image src="../../static/icons/dan.png"></image>
					<p>员工投诉</p>
				</view>
				<view class="someting">
					<image src="../../static/icons/dan.png"></image>
					<p>平台反馈</p>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				r1:true,
				r2:false,
				r3:false,
				r4:false,
				r5:false,
				spe1:"spe",
				spe2:"",
				spe3:"",
				spe4:"",
				spe5:""
			}
		},
		methods: {
			clearRight(){
				this.r1 = false;
				this.r2 = false;
				this.r3 = false;
				this.r4 = false;
				this.r5 = false;
				this.spe1 = "";
				this.spe2 = "";
				this.spe3 = "";
				this.spe4 = "";
				this.spe5 = "";
			},
			r1r(){
				this.clearRight();
				this.r1 = true;
				this.spe1 = "spe"
			},
			r2r(){
				this.clearRight();
				this.r2 = true;
				this.spe2 = "spe";
			},
			r3r(){
				this.clearRight();
				this.r3 = true;
				this.spe3 = "spe";
			},
			r4r(){
				this.clearRight();
				this.r4 = true;
				this.spe4 = "spe";
			},
			r5r(){
				this.clearRight();
				this.r5 = true;
				this.spe5 = "spe";
			}
		}
	}
</script>

<style>
	.top {
		height: var(--status-bar-height);
		width: 100%;
		background-color: #FFFFFF;
	}
	.all{
		display: flex;
		height: 1800rpx;
	}
	.left{
		display: flex;
		flex-direction: column;
		display: inline-block;
		height: 100%;
		width: 300rpx;
		box-shadow: #555555 0 0 1rpx 0;
	}
	.item{
		width: 100%;
		height: 150rpx;
		border-bottom: #000000 solid 1rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	#spe{
		background: #999999;
	}
	.item image{
		width: 100rpx;
		height: 100rpx;
	}
	.right{
		width: 100%;
		height: 100%rpx;
	}
	.someting{
		position: relative;
		width: 100%;
		height: 180rpx;
		border-bottom: #000000 solid 1rpx;
	}
	.someting image{
		width: 150rpx;
		height: 150rpx;
		margin-top: 15rpx;
		margin-left: 15rpx;
	}
	.someting p{
		position: absolute;
		top: 60rpx;
		left: 120rpx;
		font-size: 40rpx;
		width: 300rpx;
		height: 50rpx;
		text-align: center;
	}
</style>
