<template>
	<view class="content" >
		<firstNav></firstNav>
		<videoList :list="list"></videoList>
		<tab></tab>
		
	</view>
</template>

<script>
	import tab from "../../components/tab.vue"
	import firstNav from "../../components/first-nav.vue"
	import videoList from "../../components/videoList.vue"
	
	export default {
		data() {
			return {
				list:[]
			}
		},
		components:{
			tab,
			firstNav,
			videoList,
		},
		onLoad() {
			this.getData()
		},
		methods: {
			getData(){
				uni.request({
					url:"http://192.168.43.101:80/api/va.json",
					header:{
						
					},
					success:(res)=> {
						this.list=res.data.list
					}
					
				})
			}
		}
	}
</script>

<style>
	.content{
		width: 100%;
		height: 100vh;
	}

</style>
