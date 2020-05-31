<template>
	<view class="follwPlayer">
		<video 
		id="myVideo" 
		class="video" 
		objectFit="cover" 
		loop="true" 
		:src="'http://192.168.43.101:80/video/'+item.src" 
		:controls="false" 
		@click="PlayerTo(list)"
		>
			<cover-view class="iconfont iconbofang icon" @click="click"></cover-view>
		</video>
	</view>
</template>

<script>
	export default {
		props:['item','index','list'],
		data() {
			return {
				Play:false
			};
		},
		onReady() {
			this.videoContext=uni.createVideoContext('myVideo',this)
			/* if(this.index===0){
				this.play()
			} */
		},
		methods:{
			play(){
				if(this.Play===false){
					this.videoContext.play()
				}
				this.Play=true
			},
			pause(){
				if(this.Play===true){
					this.videoContext.pause()
				}
				this.Play=false
			},
			click(){
				if(this.Play===true){
					this.videoContext.pause()
					this.Play=false
				}else{
					this.videoContext.play()
					this.Play=true
				}
			},
			PlayerTo(res){
				uni.setStorage({
					key:'videoList',
					data:res
				})
				uni.navigateTo({
					url:'/pages/player/player'
				})
			}
		},
		
		
		
	}
</script>

<style>
.follwPlayer{
	height:100%;
	width:100%;
}
.video{
	width: 80%;
	height:100%;
	z-index:19;
	position: relative;
}
.icon{
	position: absolute;
	bottom: 10px;
	right:10px;
	color: #FFFFFF;
	font-size: 20px;
}
</style>
