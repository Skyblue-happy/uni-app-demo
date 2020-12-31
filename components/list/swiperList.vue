<template>
	<scroll-view scroll-x class="list-box">
		<view class="list-item" 
			:currentIndex="currentIndex" 
			:class="currentIndex == index?'active':''" 
			v-for="(item,index) in list"
			 :key="index" 
			 @click="chooseItem(index,item)">
			 <img :src="item.iconUrl" alt="" class="icon-img">
			<span>{{item.title}}</span>
		</view>
	</scroll-view>
</template>

<script>
	export default{
		name:'swiperList',
		data(){
			return{}
		},
		props:{
			list: {
				type: Array,
				default:[]
			},
			currentIndex:{
				type:Number,
				default:0
			}
		},
		methods:{
			chooseItem(index,item){
				let obj = {
					index,
					url:item.url
				}
				this.$emit('handleOk',obj)
				console.log(index,item)
			}
		}
	}
</script>

<style scope lang="scss">
	.active {
		background-color: lightblue !important;
		color: #007AFF;
	}
	
	.list-box {
		width: 100%;
		overflow: hidden;
		white-space: nowrap;
	}
</style>
