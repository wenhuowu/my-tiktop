<template>
	<view class="newsContent">
		<view class="box">
			<view class="icon" v-for="item in iconList" :key="item.id">
				<view class="box-img">
					<image class="img" :src="item.src" mode=""></image>
				</view>
				<view class="icon-text">
					{{item.text}}
				</view>
			</view>
		</view>
		<view class="newsList">
			<view class="item" v-for="item in newsList" :key="item.id">
				<view class="author-img-box">
					<image class="author-img" src="../static/img/author.jpg" mode=""></image>
				</view>
				<view class="text">
					<view class="top">
						<view class="name">
							{{item.name}}
						</view>
						<view class="time">
							{{item.time}}
						</view>
					</view>
					<view class="content">
						{{item.content}}。
					</view>
				</view>
			</view>
			<view class="bot-box">
				<view class="more">
					无更多消息
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				newsList:[
					{
						id:1,
						name:"张三",
						time:'8-1',
						content:'你好，我是张三。我特别爱吃！！！'
					},
					{
						id:2,
						name:"李四",
						time:'8-2',
						content:'你好，我是李四。我特别爱睡觉！！！'
					},
					{
						id:3,
						name:"王二麻",
						time:'8-1',
						content:'你好，我是王二麻。我特别爱购物！！！'
					},
					{
						id:4,
						name:"狗剩儿",
						time:'8-1',
						content:'你好，我是狗剩儿。我特别爱运功！！！'
					},
					{
						id:4,
						name:"文火",
						time:'8-1',
						content:'你好，我是文火。我热爱学习'
					}
				],
				iconList:[
					{
						id:1,
						src:'../static/img/fans.jpg',
						text:"粉丝"
					},
					{
						id:2,
						src:'../static/img/love.jpg',
						text:"点赞"
					},
					{
						id:3,
						src:'../static/img/comment.jpg',
						text:"评论和@"
					},
					{
						id:4,
						src:'../static/img/dong.jpg',
						text:"随拍互动"
					}
				]
			};
		}
	}
</script>

<style>
.newsContent{
	width: 100%;
	background: #000000;
}
.box{
	width: 100%;
	height: 240rpx;
}
.icon{
	width: 25%;
	height: 200rpx;
	float: left;
	margin: 0 auto;
}
.box-img{
	text-align: center;
}
.img{
	width: 80rpx;
	height: 80rpx;
	border-radius: 10rpx;
	margin-top: 40rpx;
}
.icon-text{
	font-size: 26rpx;
	text-align: center;
	color: #eee;
	margin-top: 20rpx;
}
.newsList{
	background: #000000;
}
.item{
	height: 120rpx;
	padding: 30rpx 20rpx;
}
.author-img-box{
	float: left;
	margin-left: 20rpx;
}
.author-img{
	width: 90rpx;
	height: 90rpx;
	border-radius: 50%;
}
.text{
	float: left;
	margin-left: 30rpx;
	height: 30rpx;
	width:75%;
	color: #FFFFFF;
}
.top{
	height: 50rpx;
	line-height: 50rpx;
}
.name{
	float: left;
	font-size: 36rpx;
}
.time{
	float: right;
	font-size: 22rpx;
	color:#AAAAAA;
}
.content{
	height: 50rpx;
	line-height: 50rpx;
	font-size: 26rpx;
	color:#AAAAAA;
}
.bot-box{
	height: 200rpx;
	width: 100%;
}
.more{
	width: 100%;
	height: 100rpx;
	line-height: 100rpx;
	font-size: 24rpx;
	color: #AAAAAA;
	text-align: center;
}
</style>
