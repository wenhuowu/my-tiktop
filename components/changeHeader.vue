<template>
	<view class="">
		<view class="changeHeader">
			<navigator open-type="navigateBack" class="iconfont iconchahao left"></navigator>
			<view class="title">
				切换城市
			</view>
		</view>
		<view class="ground"></view>
	</view>	
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style>
.changeHeader{
	width: 100%;
	height: 120rpx;
	line-height: 160rpx;
	position:fixed;
	top:0;
	left:0;
	margin: 0 auto;
	background: #000000;
}
.ground{
	width: 100%;
	height: 120rpx;
}
.left{
	position: absolute;
	top:0;
	left:30rpx;
	height: 160rpx;
	line-height: 160rpx;
	color: #AAAAAA;
	font-size: 36rpx;
}
.title{
	font-size:26rpx;
	text-align: center;
	color: #FFFFFF;
}
</style>
