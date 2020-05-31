<template>
	<view class="listLeft">
		<view class="author">
			{{item.author}}
		</view>
		<view class="title">
			{{item.title}}
		</view>
		<view class="box">
			<view class="music">
				@月光下跳舞，婀娜多姿@
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:['item'],
		data() {
			return {
				
			};
		}
	}
</script>

<style>
.listLeft{
	height: 150rpx;
	margin-left:3rpx ;
	color:#FFFFFF;
	width:150rpx
}
.author{
	height: 70rpx;
	line-height: 70rpx;
	font-size: 30rpx;
}
.title{
	line-height: 44rpx;
	font-size: 24rpx;
	width:100%;
	word-wrap: break-word;
}
.box{
	width:200rpx;
	overflow: hidden;
}
.music{
	height: 70rpx;
	line-height: 70rpx;
	font-size: 24rpx;
	width: 280rpx;
	animation: music 4s linear 0.2s infinite;
}

@keyframes music{
	0%{
		transform:translate3d(80%,0,0)
	}
	100%{
		transform:translate3d(-80%,0,0)
	}
}
</style>
