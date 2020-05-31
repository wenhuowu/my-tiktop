<template>
	<view class="personal">
		<personal-info @change="change"></personal-info>
		<view class="" v-show="show==='作品'">
			<personal-list ></personal-list>
		</view>
		<view class="" v-show="show==='喜欢'">
			<personal-list ></personal-list>
		</view>
		<view class="" v-show="show==='动态'">
			<follow-list  :list="list"></follow-list>
		</view>
		<tab></tab>
	</view>
</template>

<script>
	import tab from '../../components/tab.vue'
	import personalInfo from '../../components/personalInfo.vue'
	import personalList from '../../components/personalList.vue'
	import followList from '../../components/followList.vue'
	export default {
		components:{
			tab,
			personalInfo,
			personalList,
			followList
		},
		data() {
			return {
				list:[],
				show:"作品",
				pages:"personal"
			}
		},
		methods: {
			getVideoInfo(){
				uni.request({
					url:'http://192.168.43.101:80/api/videos.json',
					success: (res) => {
						this.list=res.data.list
					}
				})
			},
			change(res){
				this.show=res
			}
			
		},
		created() {
			this.getVideoInfo()
		}
		
	}
</script>

<style>
.personal{
	width: 100%;
	height: 100%;
	background: #000000;
}
</style>
