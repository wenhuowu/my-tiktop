<template>
	<view class="personalInfo">
		<view class="background-img-box">
			<image class="background-img" src="../static/img/background.jpg" mode=""></image>
		</view>
		<view class="top">
			<view class="personal-img-box">
				<image class="personal-img" src="../static/img/author.jpg" mode=""></image>
			</view>
			<view v-if="pages==='user'" :style="style4" class="change" @click="change">
			 <text v-show="changeContent==='关注'" class="iconfont iconjiahao"></text>	{{changeContent}}
			</view>
			<view v-else class="change" @click="changeInfo">
				编辑资料
			</view>
		</view>
		<view class="name-box">
			<view class="name">
				文火
			</view>
			<view class="douyinId">
				抖音号:1e243141
			</view>
		</view>
		<view class="text-box">
			<view class="introduce">
				我爱睡觉
			</view>
			<view class="label-box">
				<view class="label">
					广东工业大学
				</view>
				<view class="label">
					深圳
				</view>
			</view>
			<view class="number-box">
				<view class="box">
					<text class="number">123</text>
					<text class="number-text">获赞</text>
				</view>
				<view class="box">
					<text class="number">13452</text>
					<text class="number-text">关注</text>
				</view>
				<view class="box">
					<text class="number">1235</text>
					<text class="number-text">粉丝</text>
				</view>
			</view>
		</view>
		<view class="add-box">
			<text class="iconfont iconxiangji"></text>
			<text class="add">添加随拍</text>
		</view>
		<view class="option-box">
			<view class="option" :style="style1" @click="click('作品')">
				作品
			</view>
			<view class="option" :style="style2" @click="click('动态')">
				动态
			</view>
			<view class="option" :style="style3" @click="click('喜欢')">
				喜欢
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:['pages'],
		data() {
			return {
				style1:'border-bottom:3px solid #F0AD4E;',
				style2:'',
				style3:'',
				style4:'background:red',
				changeContent:"关注"
			};
		},
		methods:{
			click(res){
				switch (res){
					case "作品":
					this.style1='border-bottom:3px solid #F0AD4E;'
					this.style2=""
					this.style3=""
					this.$emit('change',res)
						break;
					case "动态":
					this.style2='border-bottom:3px solid #F0AD4E;'
					this.style3=""
					this.style1=""
					this.$emit('change',res)
						break;
					case "喜欢":
					this.style3='border-bottom:3px solid #F0AD4E;'
					this.style2=""
					this.style1=""
					this.$emit('change',res)
						break;
					default:
						break;
				}
				
			},
			changeInfo(){
				uni.navigateTo({
					url:'/pages/changeInfo/changeInfo'
				})
			},
			change(){
				this.style4=this.style4===''?"background:red":''
				this.changeContent=this.changeContent==='关注'?"取消关注":'关注'
			}
			
		}
		
	}
</script>

<style scoped>
.personalInfo{
	width:100%;
	background: #000000;
	position: relative;
}
.background-img-box{
	width: 100%;
	padding: 0 2rpx;
	z-index:19;
}
.background-img{
	width: 100%;
	height: 360rpx;
}
.top{
	width:100%;
	position:absolute;
	top:280rpx;
	left:0;
	z-index:20;
	background:#000000;
	height:120rpx;
}
.personal-img-box{
	margin:-50rpx 0 0 60rpx;
}
.personal-img{
	width:160rpx;
	height:160rpx;
	border-radius:50%;
	z-index:20;
	border:7rpx solid #000000;
}
.change{
	position:absolute;
	top:30rpx;
	right:50rpx;
	width:55%;
	height:70rpx;
	line-height:70rpx;
	font-size:32rpx;
	text-align:center;
	background:#333333;
	border-radius:4rpx;
	color:#ffffff;
}
.name-box{
	padding:0 50rpx;
	color:#EEEEEE;
	z-index:20;
	margin-top:40rpx;
}
.name{
	height: 100rpx;
	line-height: 100rpx;
	font-size:52rpx;
}
.douyinId{
	height: 50rpx;
	line-height: 50rpx;
	font-size: 28rpx;
}
.text-box{
	z-index:20;
	padding:0 50rpx;
	margin-top: 16rpx;
	border-top: 2rpx solid #222222;
}
.introduce{
	height: 60rpx;
	line-height: 60rpx;
	font-size: 30rpx;
	color: #EEEEEE;
}
.label-box{
	width: 100%;
	height: 50rpx;
	margin-top: 10rpx;
	line-height: 50rpx;
	color: #EEEEEE;
}
.label{
	height: 40rpx;
	padding: 0 10rpx;
	line-height: 40rpx;
	font-size: 23rpx;
	background: #333333;
	color: #999999;
	float: left;
	border-radius: 3rpx;
	margin-right: 20rpx;
}
.number-box{
	width: 100%;
	height: 100rpx;
	line-height: 100rpx;
}
.box{
	height: 80rpx;
	line-height: 80rPX;
	float: left;
	margin-right: 25rpx;
}
.number{
	color: #FFFFFF;
	font-size: 30rpx;
}
.number-text{
	color: #999999;
	font-size: 26rpx;
	width:200rpx;
}
.add-box{
	margin: 0 6%;
	height:80rpx;
	line-height: 80rpx;
	background: #333333;
	border-radius: 6rpx;
	text-align: center;
	color: #FFFFFF;
}
.add{
	padding-left: 10rpx;
	font-size: 26rpx;
}
.option-box{
	width: 100%;
	height:10rpx;
	line-height: 100rpx;
	margin-bottom: 20rpx;
}
.option{
	width: 33%;
	height:100rpx;
	line-height: 100rpx;
	color: #999999;
	float: left;
	text-align: center;
}
</style>
