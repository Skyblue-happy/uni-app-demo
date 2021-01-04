<template>
	<view class="list-box">
		<view  
				class="list-item"
				v-for="(item,index) in list"
				:key="index" 
				:list="list" 
				:currentIndex="currentIndex" 
				:class="currentIndex == index?'active':''" 
				@click="chooseItem(index,item)"
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
		methods:{
			chooseItem(index,item){
				
				let obj = {
					index,
					url:item.url
				}
				this.$emit('handleOk',obj)
				// console.log('click---',obj)
				// console.log('click---item',item)
				// console.log('click---index',index)
				// console.log(item,index)
			}
		}
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
