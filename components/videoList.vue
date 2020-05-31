<template>
	<view class="videoList">
		<view class="swiper-box">
			<swiper 
			class="swiper"  
			:vertical="true" 
			@change="change"
			@touchstart="touchStart"
			@touchend="touchEnd"
			>
				<swiper-item v-for="(item,index) of videos" :key="item.id">
					<view class="swiper-item" style="color:#000000">
						<videoPlayer 
						@changeClick="changeClick" 
						ref="player" 
						:video="item"
						:index="index"
						>
						</videoPlayer>
					</view>
					<view class="left-box">
						<listLeft :item="item"></listLeft>
					</view>
					<view class="right-box">
						<listRight @open="openComment" :item="item" ref="right"></listRight>
					</view>
				</swiper-item>
			</swiper>
		</view>
		<view v-show="show" class="comment-box">
			<comment @close="close"></comment>
		</view>
	</view>
</template>

<script>
	import videoPlayer from './videoPlayer.vue'
	import listLeft from './listLeft.vue'
	import listRight from './listRight.vue'
	import comment from './comment.vue'
	var time=null
	export default {
		props:['list'],
		components:{
			videoPlayer,
			listLeft,
			listRight,
			comment
		},
		data() {
			return {
				videos:[],
				pageStartY:0,
				pageEndY:0,
				page:0,
				show:false
			};
		},
		watch:{
			list(){
				this.videos=this.list
			}
		},
		methods:{
			changeClick(){
				//点赞，调用listRight方法
				this.$refs.right[0].change()
			},
			change(res){
				clearTimeout(time)
				this.page=res.detail.current
				time=setTimeout(()=>{
					if(this.pageStartY<this.pageEndY){
						this.$refs.player[this.page].player()
						this.$refs.player[this.page+1].pause()
						this.pageStartY=0
						this.pageEndY=0
					}else{
						this.$refs.player[this.page].player()
						this.$refs.player[this.page-1].pause()
						this.pageStartY=0
						this.pageEndY=0
					}
				},1)
				
			},
			touchStart(res){
				this.pageStartY=res.changedTouches[0].pageY
				
			},
			touchEnd(res){
				this.pageEndY=res.changedTouches[0].pageY
				
			},
			openComment(){
				if(this.show===false){
					this.show=true
				}
			},
			close(){
				if(this.show===true){
					this.show=false
				}
			}
		},
		
	}
</script>

<style>
.videoList{
	height:100%;
	width: 100%;
}
.swiper-box{
	height:100%;
	width: 100%;
}
.swiper{
	height:100%;
	width: 100%;
}
.swiper-item{
	height:100%;
	width: 100%;
}
.left-box{
	z-index:20;
	position:absolute;
	bottom: 125rpx;
	left: 20rpx;
}
.right-box{
	z-index:20;
	position:absolute;
	bottom: 50px;
	right: 10px;
}
.comment-box{
	position:fixed;
	bottom:0 ;
	left: 0;
	z-index:22;
	height: 500px;
	width: 100%;
}
</style>
