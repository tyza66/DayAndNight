<template>
	<view>
		<view class="top"></view>
		<view class="all">
			<view class="left">
				<view class="item" @click="r1r()" :id="spe1">
					<image src="../../static/icons/p1.png"></image>
					<p>线上自学</p>
				</view>
				<view class="item" @click="r2r()" :id="spe2">
					<image src="../../static/icons/p2.png" ></image>
					<p>线下培训</p>
				</view>
				<view class="item" @click="r3r()" :id="spe3">
					<image src="../../static/icons/p3.png"></image>
					<p>讲座</p>
				</view>
			</view>
			<view class="right" v-if="r1">
				<view class="mianfei"><p>免费资源</p></view>
				<view class="mainfei1">
					<view class="one">
						<view class="im"><image src="../../static/icons/h1.png"></image></view>
						<view class="ti"><p>护理教学1</p></view>
						<view class="up"><p>观看：1000</p></view>
					</view>
					<view class="one">
						<view class="im"><image src="../../static/icons/h2.png"></image></view>
						<view class="ti"><p>护理教学2</p></view>
						<view class="up"><p>观看：900</p></view>
					</view>
					<view class="one">
						<view class="im"><image src="../../static/icons/h3.png"></image></view>
						<view class="ti"><p>护理教学3</p></view>
						<view class="up"><p>观看：900</p></view>
					</view>
					<view class="one">
						<view class="im"><image src="../../static/icons/h4.png"></image></view>
						<view class="ti"><p>护理教学4</p></view>
						<view class="up"><p>观看：780</p></view>
					</view>
					<view class="one">
						<view class="im"><image src="../../static/icons/h5.png"></image></view>
						<view class="ti"><p>护理教学5</p></view>
						<view class="up"><p>观看：640</p></view>
					</view>
					<view class="one">
						<view class="im"><image src="../../static/icons/h6.png"></image></view>
						<view class="ti"><p>护理教学6</p></view>
						<view class="up"><p>观看：530</p></view>
					</view>
				</view>
				<view class="mianfei"><p>付费资源</p></view>
					<view class="mainfei1">
						<view class="one">
							<view class="im"><image src="../../static/icons/h1.png"></image></view>
							<view class="ti"><p>护理教学1</p></view>
							<view class="up"><p>观看：1000</p></view>
						</view>
						<view class="one">
							<view class="im"><image src="../../static/icons/h2.png"></image></view>
							<view class="ti"><p>护理教学2</p></view>
							<view class="up"><p>观看：900</p></view>
						</view>
						<view class="one">
							<view class="im"><image src="../../static/icons/h3.png"></image></view>
							<view class="ti"><p>护理教学3</p></view>
							<view class="up"><p>观看：900</p></view>
						</view>
						<view class="one">
							<view class="im"><image src="../../static/icons/h4.png"></image></view>
							<view class="ti"><p>护理教学4</p></view>
							<view class="up"><p>观看：780</p></view>
						</view>
						<view class="one">
							<view class="im"><image src="../../static/icons/h5.png"></image></view>
							<view class="ti"><p>护理教学5</p></view>
							<view class="up"><p>观看：640</p></view>
						</view>
						<view class="one">
							<view class="im"><image src="../../static/icons/h6.png"></image></view>
							<view class="ti"><p>护理教学6</p></view>
							<view class="up"><p>观看：530</p></view>
						</view>
					</view>
				</view>
				<view class="right" v-if="r2">
					
					<view class="dingwei">
						<image src="../../static/icons/dingwei.png"></image>
						<p @click="gps()"><u>{{gp}}</u></p>
					</view>
					<p>{{wei}}</p><u>{{wei2}}</u><p>{{wei3}}</p>
					<image class="gps" src="../../static/icons/ddd.png">
				</view>
				<view class="right" v-if="r3">
					<view class="mianfei"><p>免费资源</p></view>
					<view class="mainfei1">
						<view class="one">
							<view class="im"><image src="../../static/icons/h5.png"></image></view>
							<view class="ti"><p>护理讲座1</p></view>
							<view class="up"><p>观看：1000</p></view>
						</view>
						<view class="one">
							<view class="im"><image src="../../static/icons/h5.png"></image></view>
							<view class="ti"><p>护理讲座2</p></view>
							<view class="up"><p>观看：900</p></view>
						</view>
						
					</view>
				</view>
				<view class="right" v-if="r4">
				</view>
				<view class="right" v-if="r5">
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
				wei:"正在获取您的线下培训位置...",
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
				this.wei = "根据您的位置，推荐您参与";
				this.wei2 = "辽宁省锦州市太和区渤海大学滨海校区文科楼aj105";
				this.wei3 = "课程";
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
	.mianfei{
		width: 100%;
		height: 100rpx;
		background: #999999;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.one{
		float: left;
		height: 300rpx;
		width: 49%;
		margin-left: 1%;
		margin-top: 10rpx;
		border-radius: 10rpx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		background: #F8F8F8;
	}
	.one .im{
		width: 100%;
		height: 60%;
	}
	.one .im image{
		width: 100%;
		height: 100%;
	}
	.one .ti{
		width: 100%;
		height: 20%;
	}
	.one .ti p{
		text-align: center;
		width: 100%;
		height: 20%;
	}
	.one .up{
		width: 100%;
		height: 20%;
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
		width: 500rpx;
		height: 300rpx;
	}
</style>
