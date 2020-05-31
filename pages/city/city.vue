<template>
	<view class="city">
		<tab></tab>
		<first-nav></first-nav>
		<city-content :tcity="tcity"></city-content>
	</view>
</template>

<script>
	import tab from '../../components/tab.vue'
	import firstNav from '../../components/first-nav.vue'
	import cityContent from '../../components/cityContent.vue'
	export default {
		components:{
			tab,
			firstNav,
			cityContent
		},
		data() {
			return {
				tcity:"深圳"
			}
		},
		methods: {
			
		},
		onShow() {
			uni.getStorage({
				key:'city',
				success: (res) => {
					this.tcity=res.data
				}
			})
		}
	}
</script>

<style>
.city{width: 100%;height: 100%;background: #000000;}
</style>
