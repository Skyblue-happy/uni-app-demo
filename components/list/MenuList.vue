<template>
	<view>
		<view v-for="(item,index) in menus" :key="index" class="list-item">
			<p>{{index +1}}、{{item.title}} 、<slot name="listDate" :item="item">{{item.date}}</slot> </p>
		</view>
		<view>
			<p>this is <span style="color:#007AFF;margin-left: 10px;">{{onName}}</span></p>
			<slot name="slotNameDemo"></slot>
		</view>
		<view>
			<p>before title:{{title}}</p>
			<button @click="changeTitle">click me</button>
		</view>
	</view>
</template>

<script>
	export default{
		name:"MenuList",
		props:{
			menus:{
				type:Array,
				default:[]
			},
			name:{
				type:String
			},
			title:{
				type:String
			}
		},
		computed:{
			onName:function(){
				return this.name.toUpperCase()
			}
		},
		methods:{
			changeTitle(){
				this.$emit('update:title',"changed text to new ")
			}
		}
	}
</script>

<style scoped lang="scss">
	.list-item{
		padding: 5px 10px;
	}
	// odd 奇数项
	.list-item:nth-child(odd){
		background-color: lightblue;
	}
</style>
