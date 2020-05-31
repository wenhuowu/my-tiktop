<template>
	<view class="changeList">
		<scroll-view class="scrolly" scroll-y="true" :scroll-into-view="viewId">
			<view class="city-box">
				<view class="box">
					<view class="title">
						<icon class="iconfont icondingwei"></icon>
						当前城市
					</view>
					<view class="currentCity">{{tcity}}</view>
				</view>
				<view class="box">
					<view class="title">
						热门城市
					</view>
					<view class="hotlist">
						<view class="item" v-for="(item,index) in list" :key="index" @click="click(item)">
							{{item}}
						</view>
					</view>
				</view>
				<view class="box-list" v-for="(cities,index) in city" :key="index">
					<view class="initial" :id="cities.initial">
						{{cities.initial}}
					</view>
					<view 
					class="city-name" 
					v-for="item in cities.list" 
					:key="cities.initial"
					@click="click(item.name)">
						{{item.name}}
					</view>
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	export default {
		props:['city','letter'],
		data() {
			return {
				list:['北京','深圳','上海','成都','广州','重庆','西安','苏州','武汉','杭州','郑州','南京'],
				viewId:'',
				tcity:"深圳"
			};
		},
		
		methods:{
			click(res){
				console.log(res)
				uni.setStorage({
					key:'city',
					data:res
				})
				uni.getStorage({
					key:'city',
					success: (res) => {
						this.tcity=res.data
					}
				})
				uni.switchTab({
					url:'/pages/city/city'
				})
				
			}
		},
		watch:{
			letter(){
				
				this.viewId=this.letter
				console.log(this.viewId)
			},
		}
	}
</script>

<style>
.changeList{
	width: 100%;
	background: #000000;
	z-index: 19;
	height: 100%;
}
.box{
	background: #0b0b0b;
	margin-top: 20rpx;
	padding:0 5px 20px 5px
}
.title{
	height: 80rpx;
	line-height: 80rpx;
	margin-left: 30rpx;
	color: #FFFFFF;
	font-size: 28rpx;
}
.currentCity{
	color: #AAAAAA;
	font-size: 30rpx;
	margin-left: 30rpx;
	height:50rpx;
	line-height: 50rpx;
}
.hotlist{
	width:100%;
	overflow: hidden;	
}
.item{
	width:30%;
	height:56rpx;
	line-height: 56rpx;
	font-size: 27rpx;
	float: left;
	background: #333333;
	margin-left:2.5%;
	margin-bottom: 20rpx;
	text-align: center;
	color: #AAAAAA;
}
.box-list{
	padding: 16rpx 10rpx;
}
.initial{
	height: 50rpx;
	line-height: 50rpx;
	background: #000000;
	padding-left: 20rpx;
	color: #666666;
	font-size: 24rpx;
}
.city-name{
	background: #222222;
	height: 80rpx;
	line-height: 80rpx;
	padding-left: 20rpx;
	color: #AAAAAA;
	font-size: 30rpx;
}
.scrolly{
	height: 100vh;
}

		  
</style>
