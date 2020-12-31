<template>
	<view class="list-box">
		<view  
			class="list-item"
			:list="list" 
			v-for="(item,index) in list" 
			:key="index" 
			:currentIndex="currentIndex" 
			:class="currentIndex == index?'active':''" 
			 >
			<img :src="item.iconUrl" alt="" class="icon-img">
			<span>{{item.title}}</span>
		</view>
	</view>
</template>

<script>
	export default{
		name:'allList',
		data(){
			return{}
		},
		props:{
			list:{
				type:Array,
				default:[]
			},
			currentIndex:{
				type:Number,
				default:0
			}
		},
	}
</script>

<style scoped lang="scss">
	.active {
		background-color: lightblue !important;
		color: #007AFF;
	}
	
	.list-box {
	
		.list-item {
			display: inline-block;
			margin-right: 10px;
			margin-bottom: 10px;
			padding: 5px 15px;
			box-sizing: border-box;
			border-radius: 15px;
			background-color: rgb(246, 246, 246);
		}
		.net-content{
			margin: 20px auto;
			width: 90%;
		}
	}
</style>
