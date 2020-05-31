<template>
	<view class="city">
		<change-header></change-header>
		<change-list :letter="letter" :city="city" :tcity="tcity"></change-list>
		<change-alphabet @change="change" :city="city"></change-alphabet>
	</view>
</template>

<script>
	import changeHeader from'../../components/changeHeader.vue'
	import changeList from'../../components/changeList.vue'
	import changeAlphabet from'../../components/changeAlphabet.vue'
	export default {
		components:{
			changeHeader,
			changeList,
			changeAlphabet
		},
		data() {
			return {
				city:[],
				letter:[],
				tcity:""
			}
		},
		onShow(){
			uni.getStorage({
				key:'city',
				success: (res) => {
					this.tcity=res.data || "深圳"
				}
			})
		},
		methods: {
			getCityInfo(){
				uni.request({
					url:'http://192.168.43.101:80/api/city.json',
					success: (res) => {
						this.city=res.data.city
					}
				})
			},
			change(res){
				this.letter=res
			}
		},
		created() {
			this.getCityInfo()
		}
	}
</script>

<style>
.city{
	width:100%;
	background: #000000;
	height: 100%;
}
</style>
