<template>
	<view  class="cityContent">
		<view class="conlation">
			<view class="iconfont icondingwei conlation-left">
				自动定位：{{tcity}}
			</view>
			<navigator  url="/pages/changeCity/changeCity" class="conlation-right">
				切换<text class="iconfont iconchangyongicon-"></text>
			</navigator>
		</view>
		<view class="video-list">
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="fill" 
					src="http://192.168.43.101:80/video/2-1.mp4" >
					</video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" ></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="fill" 
					src="http://192.168.43.101:80/video/2-2.mp4" >
					</video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" ></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="fill" 
					src="http://192.168.43.101:80/video/2-3.mp4" >
					</video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" ></image>
				</view>
			</view>
			<view class="item">
				<view class="video">
					<video 
					style="width: 100%;height: 100%;" 
					objectFit="cover" 
					src="http://192.168.43.101:80/video/2-1.mp4" >
					</video>
				</view>
				<view class="img">
					<image class="image-box" src="../static/img/author.jpg" ></image>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:['tcity'],
		data() {
			return {
				
			};
		}
	}
</script>

<style>
.cityContent{
	width: 100%;
	background: #000000;
	
}
.conlation{
	width: 100%;
	height: 40px;
	padding-top:70px;
	overflow: hidden;
	color: #aaaaaa;
}
.conlation-right{
	float: right;
	font-size:13px ;
	padding-right: 15px;
}
.conlation-left{
	float: left;
	font-size:13px ;
	padding-left: 15px;
}
.video-list{
	width: 100%;
	overflow: auto;
	background: #000000;
}
.item{
	width: 50%;
	float: left;
	position: relative;
}
.video{
	width: 92%;
	height:300px;
	margin-left:4%;
	z-index:18;
	
}
.img{
	position: absolute;
	bottom: 7px;
	right: 15px;
}
.image-box{
	width: 30px;
	height: 30px;
	border-radius: 50%;
}
</style>
