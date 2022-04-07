<template>
	<view>
		<view class="top"></view>
		<view class="swiper-c">
			<swiper indicator-dots="true" autoplay="autoplay" interval="1000" duration="500">
				<swiper-item>
					<image src="../../static/picture/pi1.png"></image>
				</swiper-item>
				<swiper-item>
					<image src="../../static/picture/pi2.png"></image>
				</swiper-item>
				<swiper-item>
					<image src="../../static/picture/pi3.png"></image>
				</swiper-item>
				<swiper-item>
					<image src="../../static/picture/pi4.png"></image>
				</swiper-item>
				<swiper-item>
					<image src="../../static/picture/pi5.png"></image>
				</swiper-item>
			</swiper>
		</view>
		<view class="someitem">
			<view class="item">
				<image src="../../static/icons/i1.png"></image>
				<p>专属护工</p>
			</view>
			<view class="item">
				<image src="../../static/icons/i3.png"></image>
				<p>养老院</p>
			</view>
			<view class="item">
				<image src="../../static/icons/i2.png"></image>
				<p>健康知识</p>
			</view>
			<view class="item">
				<image src="../../static/icons/i4.png"></image>
				<p>讨论圈</p>
			</view>
		</view>
		<view class="swiper-c2">
			<swiper vertical="true" autoplay="autoplay" interval="1500" duration="500">
				<swiper-item>
					<view>
						<p class="a1">公告</p>
						<p class="a2">当前软件为测试阶段，可雇佣护工数量可能有限...</p>
					</view>
					<view>
						<p class="a1">公告</p>
						<p class="a2">想申请成为护工？点击这里下载护工端...</p>
					</view>
				</swiper-item>
				<swiper-item>
					<view>
						<p class="a1">号召</p>
						<p class="a2">热馨护工竞选比赛正在进行，快进来给你喜欢的...</p>
					</view>
					<view>
						<p class="a1">号召</p>
						<p class="a2">快来参与用户喜好调查和用户满意度调查...</p>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<view class="someting"> 
			<image src="../../static/icons/da.png"></image>
			<p>张小明，金牌护工，短期，已结100单，好评多</p>
		</view>
		<view class="someting">
			<image src="../../static/icons/da.png"></image>
			<p>刘韩月，特级护工，好评多，按摩好评大奖赛冠军</p>
		</view>
		<view class="someting"> 
			<image src="../../static/icons/da.png"></image>
			<p>金海明，职业护工，按摩培训讲师下线接单</p>
		</view>
		<view class="someting">
			<image src="../../static/icons/da.png"></image>
			<p>王三柳，金牌护工，长期，包月</p>
		</view>
		<view class="someting">
			<image src="../../static/icons/da.png"></image>
			<p>王二民，实习护工，短期</p>
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

		},
		methods: {

		}
	}
</script>

<style>
	.top {
		height: var(--status-bar-height);
		width: 100%;
		background-color: #FFFFFF;
	}
	.swiper-c{
		width: 100%;
		height: 400rpx;
	}
	.swiper-c swiper{
		width: 100%;
		height: 100%;
	}
	.swiper-c swiper swiper-item image{
		width: 100%;
		height: 100%;
	}
	.someitem{
		width: 100%;
		height: 160rpx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
	.someitem .item{
		width: 120rpx;
		height: 120rpx;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.item image{
		width: 80rpx;
		height: 80rpx;
	}
	.item p{
		font-size: 25rpx;
		text-align: center;
		color: #555555;
	}
	.swiper-c2{
		width: 100%;
		height: 100rpx;
	}
	.swiper-c2 swiper{
		width: 100%;
		height: 100%;
	}
	.swiper-c2 swiper swiper-item view{
		height: 50%;
		display: flex;
		flex-direction: row;
		align-items: center;
	}
	.a1{
		font-size: 15rpx;
		text-align: center;
		color: #DD524D;
		width: 65rpx;
		height: 65%;
		border: #DD524D solid 1px;
		border-radius: 15rpx;
		margin-left: 20rpx;
	}
	.a2{
		text-align: center;
		font-size: 15rpx;
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
		left: 180rpx;
		font-size: 40rpx;
		width: 580rpx;
		height: 50rpx;
	}
</style>
