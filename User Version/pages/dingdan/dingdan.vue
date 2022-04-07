<template>
	<view>
		<view class="top"></view>
		<view class="bg"></view>
		<view class="kuang">
			<view class="p1">
				<radio :checked="r1" @click="r1r()"></radio>护工：李芳
				<p @click="bianji()">编辑</p>
			</view>
			<view class="p2" v-show="!shanchu11">
				<radio :checked="r2" @click="r2r()"></radio>
				<image src="../../static/icons/jiayou.png"></image>
				<p class="xiangmu">按摩</p>
				<p class="shuoming">时间：2022.3.10 10：00 地点：渤海大学滨海校区</p>
				<p class="jiage">￥100</p>
				<view class="delete" v-show="show" @click="shanchu1()"><p>删除</p></view>
			</view>
			<view class="p2" v-show="!shanchu22">
				<radio :checked="r3" @click="r3r()"></radio>
				<image src="../../static/icons/jiayou.png"></image>
				<p class="xiangmu">按摩</p>
				<p class="shuoming">时间：2022.3.10 13：00 地点：渤海大学滨海校区</p>
				<p class="jiage">￥100</p>
				<view class="delete" v-show="show" @click="shanchu2()"><p>删除</p></view>
			</view>
		</view>
		<view class="kuang">
			<view class="p1">
				<radio :checked="r4" @click="r4r()"></radio>护工：刘涵
				<p @click="bianji()">编辑</p>
			</view>
			<view class="p2" v-show="!shanchu33">
				<radio :checked="r5" @click="r5r()"></radio>
				<image src="../../static/icons/jiayou.png"></image>
				<p class="xiangmu">按摩</p>
				<p class="shuoming">时间：2022.3.10 15：00 地点：渤海大学滨海校区</p>
				<p class="jiage">￥100</p>
				<view class="delete" v-show="show" @click="shanchu3()"><p>删除</p></view>
			</view>
		</view>
		<view class="kuang">
			<view class="p1">
				<radio :checked="r6" @click="r6r()"></radio>护工：张伟
				<p @click="bianji()">编辑</p>
			</view>
			<view class="p2" v-show="!shanchu44">
				<radio :checked="r7" @click="r7r()"></radio>
				<image src="../../static/icons/jiayou.png"></image>
				<p class="xiangmu">按摩</p>
				<p class="shuoming">时间：2022.3.10 17：00 地点：渤海大学滨海校区</p>
				<p class="jiage">￥100</p>
				<view class="delete" v-show="show" @click="shanchu4()"><p>删除</p></view>
			</view>
			<view class="p2" v-show="!shanchu55">
				<radio :checked="r8" @click="r8r()"></radio>
				<image src="../../static/icons/jiayou.png"></image>
				<p class="xiangmu">奥利</p>
				<p class="shuoming">时间：2022.3.10 19：00 地点：渤海大学滨海校区</p>
				<p class="jiage">￥100</p>
				<view class="delete" v-show="show" @click="shanchu5()"><p>删除</p></view>
			</view>
		</view>
		<view class="pay">
			<view class="radio"><radio :checked="all" @click="allr()"></radio>全选</view>
			<p class="heji">合计：</p>
			<p class="jine">{{sum}}</p>
			<view class="jiesuan"><p>结算({{shu}})</p></view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				r1: false,
				r2: false,
				r3: false,
				r4: false,
				r5: false,
				r6: false,
				r7: false,
				r8: false,
				all: false,
				sum: "0.00",
				shu: 0,
				show: false,
				shanchu11: false,
				shanchu22: false,
				shanchu33: false,
				shanchu44: false,
				shanchu55: false,
			}
		},
		methods: {
			suanqian(){
				var summ = 0;
				if(this.r2==true) summ += 100;
				if(this.r3==true) summ += 100;
				if(this.r5==true) summ += 100;
				if(this.r7==true) summ += 100;
				if(this.r8==true) summ += 100;
				this.sum = summ;
				var summm = 0;
				if(this.r2==true) summm += 1;
				if(this.r3==true) summm += 1;
				if(this.r5==true) summm += 1;
				if(this.r7==true) summm += 1;
				if(this.r8==true) summm += 1;
				this.shu = summm;
			},
			r1r(){
				if(this.r1==false){
					this.r1 = true;
					this.r2 = true;
					this.r3 = true;
				}else{
					this.r1 = false;
					this.r2 = false;
					this.r3 = false;
				}
				this.suanqian();
			},
			r2r(){
				this.r2 = !this.r2;
				if(this.r2==true&&this.r3==true){
					this.r1 = true;
				}else{this.r1 = false;}
				this.suanqian();
			},
			r3r(){
				this.r3 = !this.r3;
				if(this.r2==true&&this.r3==true){
					this.r1 = true;
				}else{this.r1 = false;}
				this.suanqian();
			},
			r4r(){
				if(this.r4==false){
					this.r4 = true;
					this.r5 = true;
				}else{
					this.r4 = false;
					this.r5 = false;
				}
				this.suanqian();
			},
			r5r(){
				this.r5 = !this.r5;
				if(this.r5==true){
					this.r4 = true;
				}else{this.r4 = false;}
				this.suanqian();
			},
			r6r(){
				if(this.r6==false){
					this.r6 = true;
					this.r7 = true;
					this.r8 = true;
				}else{
					this.r6 = false;
					this.r7 = false;
					this.r8 = false;
				}
				this.suanqian();
			},
			r7r(){
				this.r7 = !this.r7;
				if(this.r7==true&&this.r8==true){
					this.r6 = true;
				}else{this.r6 = false;}
				this.suanqian();
			},
			r8r(){
				this.r8 = !this.r8;
				if(this.r7==true&&this.r8==true){
					this.r6 = true;
				}else{this.r6 = false;}
				this.suanqian();
			},
			allr(){
				if(this.all==false){
					this.r1 = true;
					this.r2 = true;
					this.r3 = true;
					this.r4 = true;
					this.r5 = true;
					this.r6 = true;
					this.r7 = true;
					this.r8 = true;
					this.all = true;
				}
				else{
					this.r1 = false;
					this.r2 = false;
					this.r3 = false;
					this.r4 = false;
					this.r5 = false;
					this.r6 = false;
					this.r7 = true;
					this.r8 = true;
					this.all = false;
				}
				this.suanqian();
			},
			bianji(){
				this.show = !this.show;
			},
			shanchu1(){
				this.shanchu11 = true;
			},
			shanchu2(){
				this.shanchu22 = true;
			},
			shanchu3(){
				this.shanchu33 = true;
			},
			shanchu4(){
				this.shanchu44 = true;
			},
			shanchu5(){
				this.shanchu55 = true;
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
	.bg{
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: #C0C0C0;
	}
	.pay{
		width: 100%;
		height: 200rpx;
		position: fixed;
		bottom: 0;
		background: white;
		box-shadow: #999999 0 -1rpx 0 0 ;
		z-index: 30;
	}
	.pay .radio{
		position: absolute;
		left: 10rpx;
		top: 40rpx;
	}
	.kuang{
		float: left;
		position: relative;
		width: 100%;
		background: white;
		z-index: 20;
		margin-top: 20rpx;
	}
	.p1{
		width: 100%;
		height: 80rpx;
	}
	.p1 radio{
		margin-left: 10rpx;
		margin-top: 16rpx;
	}
	.p2{
		position: relative;
		width: 100%;
		height: 200rpx;
	}
	.p2 radio{
		position: absolute;
		left: 10rpx;
		top: 75rpx;
	}
	.p1 p{
		display: inline;
		float: right;
		margin-top: 16rpx;
		margin-right: 10rpx;
		font-size: 30rpx;
	}
	.p2 image{
		position: absolute;
		left: 60rpx;
		top: 20rpx;
		width: 160rpx;
		height: 160rpx;
	}
	.xiangmu{
		position: absolute;
		left: 250rpx;
		top: 15rpx;
	}
	.shuoming{
		position: absolute;
		left: 250rpx;
		top: 60rpx;
		line-height: 30rpx;
		background: #C8C7CC;
		color: #555555;
	}
	.jiage{
		position: absolute;
		color: gold;
		left: 250rpx;
		top: 120rpx;
	}
	.heji{
		position: absolute;
		left: 380rpx;
		top: 40rpx;
	}
	.jine{
		position: absolute;
		left: 470rpx;
		top: 40rpx;
		color: #E75603;
	}
	.jiesuan{
		float: right;
		width: 200rpx;
		height: 150rpx;
		background: #E75603;
	}
	.jiesuan p{
		color: white;
		font-size: 40rpx;
		text-align: center;
		margin-top: 40rpx;
	}
	.delete{
		position: absolute;
		width: 100rpx;
		height: 60rpx;
		left: 630rpx;
		background: red;
	}
	.delete p{
		text-align: center;
		color: #FFFFFF;
	}
</style>
