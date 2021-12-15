<template>
	<view>
		<view @click="showPicker" class="pickerStyle">{{chooseDate}}</view>
		<rangeDatePick 
			:show="isShow"
			@showchange="showchange"
			:start="start"
			:end="end"
			:value="value"
			@change="bindChange"
			@cancel="bindCancel"
			themeColor="#4C83D6"
			fields="day"
		></rangeDatePick>
	</view>
</template>

<script>
    import rangeDatePick from '@/components/pyh-rdtpicker/pyh-rdtpicker.vue';
	export default {
		data() {
            const currentDate = this.getDate({format: true})
			return {
                nowDate:currentDate,//获取当前时间
				isShow:false,
				value:[],
				chooseDate:"选择时间段",
				start:"1900-01-01",
				end:"2200-12-01"
			}
		},
		components:{
			rangeDatePick
		},
		onLoad() {
			//模拟修改start和end
			// setTimeout(()=>{
			// 	this.start = "2000-01-01";
			// 	this.end = "2022-01-01"
			// },4000)
		},
		methods: {
			showPicker(e){
				this.isShow=true
			},
			showchange(){
				this.isShow=!this.isShow;
			},
			bindChange(data){
				console.log(data)
				this.chooseDate=data[0]+"至"+data[1]
			},
			bindCancel(e){
				console.log(e)
			},
			getDate(type) {
            	const date = new Date();
            	let year = date.getFullYear();
            	let month = date.getMonth() + 1;
            	let day = date.getDate();
            	month = month > 9 ? month : '0' + month;
            	day = day > 9 ? day : '0' + day;
            	return `${year}-${month}-${day}`;
            }
		}
	}
</script>

<style>
	page{text-align: center;padding: 50upx 0;}
	.pickerStyle{font-size: 26upx;border-bottom: 1px solid #4C83D6;display: inline-block;padding: 10upx 20upx;}
</style>
