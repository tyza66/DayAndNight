<template>
	<view>
		<view class="top"></view>
		<view class="all">
			<view class="left">
				<view class="item" @click="r1r()" :id="spe1">
					<image src="../../static/icons/wenjian.png"></image>
					<p>线上初审</p>
				</view>
				<view class="item" @click="r2r()" :id="spe2">
					<image src="../../static/icons/renyuan.png" ></image>
					<p>线下复核</p>
				</view>
				<view class="item" @click="r3r()" :id="spe3">
					<image src="../../static/icons/jiangbei.png"></image>
					<p>评级结果</p>
				</view>
				<view class="item" @click="r4r()" :id="spe4">
					<image src="../../static/icons/ys.png"></image>
					<p>申请复审</p>
				</view>
				<view class="item" @click="r5r()" :id="spe5">
					<image src="../../static/icons/x5.png"></image>
					<p>意见建议</p>
				</view>
			</view>
			<view class="right" v-if="r1">
				<iframe src="https://www.wjx.cn/vm/mjgAbpz.aspx"></iframe>
			</view>
			<view class="right" v-if="r2">
				<view class="dingwei">
					<image src="../../static/icons/dingwei.png"></image>
					<p @click="gps()"><u>{{gp}}</u></p>
				</view>
				<p>{{wei}}</p><u>{{wei2}}</u><p>{{wei3}}</p>
				<image class="gps" src="../../static/icons/gps.png">
			</view>
			<view class="right" v-if="r3">
				<view class="zhanshi">
			<view class="i">
						<image src="../../static/icons/s2.png"></image>
						<p>金牌</p>
					</view>
					<view class="i">
						<image src="../../static/icons/s1.png"></image>
						<p>银牌</p>
					</view>
					<view class="i">
						<image src="../../static/icons/s3.png"></image>
						<p>铜牌</p>
					</view>
					<view class="i">
						<image src="../../static/icons/s4.png"></image>
						<p>花</p>
					</view>
					<view class="i">
						<image src="../../static/icons/s5.png"></image>
						<p>草</p>
					</view>
				</view>
				<view class="wodedengji">我的等级</view>
				<view class="jiangpai"><image class="jiangpai" src="../../static/icons/ww.jpg"></view>
				<view class="yinpai">银牌</view>
				<view class="yinpait">综合您的个人情况与资料，授予您银牌护工称号！</view>
			</view>
			<view class="right" v-if="r4">
				<view class="shuru">
					<textarea v-model="out"></textarea>
				</view>
				<view class="tijiao" @click="toa()">提交</view>
				<view class="shenhe">{{shen}}</view>
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
				spe5:"",
				gp:"北斗GPS定位",
				wei:"正在获取您的线下面试位置...",
				wei2:"",
				wei3:"",
				out:"",
				shen:""
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
			},
			gps(){
				this.gp = "辽宁省锦州市太和区渤海大学滨海校区";
				this.wei = "推荐您去";
				this.wei2 = "辽宁省锦州市太和区渤海大学滨海校区文科楼c401";
				this.wei3 = "参加线下面是复核";
			},
			toa(){
				uni.showToast({
				    title: '提交成功正在审核',
				    duration: 2000
				});
				this.shen = "审核中"
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
		height: 1200rpx;
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
		height: 100%;
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
	.right iframe{
		width: 100%;
		height: 100%;
	}
	.dingwei{
		width: 100%;
		height: 170rpx;
		display: flex;
		flex-direction: row;
		justify-content: left;
		align-items: center;
	}
	.dingwei image{
		width: 100rpx;
		height: 100rpx;
	}
	.dingwei p{
		font-size: 30rpx;
	}
	.gps{
		width: 100%;
		height: 500rpx;
	}
	.zhanshi{
		width: 100%;
		height: 200rpx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	.zhanshi .i{
		width: 90rpx;
		height: 180rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.zhanshi .i image{
		width: 80rpx;
		height: 150rpx;
	}
	.wodedengji{
		width: 140rpx;
		margin: 0 auto;
		text-align: center;
		background: red;
		border: #000000 solid 1px;
		margin-top: 50rpx;
	}
	.jiangpai{
		width: 300rpx;
		height: 300rpx;
		margin: 0 auto;
	}
	.yinpai{
		width: 140rpx;
		text-align: center;
		margin: 0 auto;
	}
	.shuru{
		width: 400rpx;
		height:	600rpx;
		margin: 0 auto;
		margin-top: 50rpx;
		background: #C8C7CC;
	}
	.shuru textarea{
		width: 100%;
		height: 100%;
	}
	.tijiao{
		width: 140rpx;
		margin: 0 auto;
		text-align: center;
		background: red;
		border: #000000 solid 1px;
		margin-top: 50rpx;
		border-radius: 5rpx;
	}
	.shenhe{
		width: 140rpx;
		margin: 0 auto;
		text-align: center;
		color: red;
	}
</style>
