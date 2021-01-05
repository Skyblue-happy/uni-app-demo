<template>
	<view class="index-content">
		<view class="index-content-tp">
			<p>2020-12-31 周四</p>
		</view>

		<view class="list-box">
			<view class="btn-show">
				<img :src="btnImgUrl" alt="" @click="switchBtn">
			</view>

			<swiper-list 
				v-show="isShow"
				:list="netList" 
				:currentIndex="selectMenuIndex"
				@handleOk="handleOk"
			 ></swiper-list>

			<all-list 
				v-show="!isShow" 
				:list="netList"  
				:currentIndex="selectMenuIndex"
				@handleOk="handleOk"
			></all-list>
		</view>
		
		<list-content class="list-content" :index="selectMenuIndex" :class="isShow?'contentHeightA':'contentHeightB'"></list-content>

		<!-- <menu-list :menus="list" :name="onName" :title.sync="title">
			<template #listDate="listDateScope">
				插槽作用域：{{listDateScope.item.date}}
			</template>
			<template v-slot:slotNameDemo>
				<p>作用域插槽&lt;template #listDate="listDateScope"&tr;</p>
				<p>好嗨哦</p>
			</template>
		</menu-list> -->
	</view>
</template>

<script>
	import SwiperList from '../../components/list/swiperList.vue'
	import AllList from '../../components/list/allList.vue'
	import ListContent from '../../components/list/listContent.vue'
	import config from '../../utils/config.js'
	
	import {
		sayName
	} from '../../utils/demo.js'
	export default {
		data() {
			return {
				date: '2020-12-30',
				list: [{
						title: 'HTML',
						date: 2000
					},
					{
						title: 'CSS',
						date: 2001
					},
					{
						title: 'JavaScript',
						date: 2002
					},
					{
						title: 'Java',
						date: 2003
					},
					{
						title: 'Node.js',
						date: 2004
					}
				],
				onName: 'girl~~',
				title: 'hello,my world',

				netList: [{
						title: '虎扑',
						iconUrl:'https://img.printf520.com/hupu.png',
						url:'https://mo.fish/?class_id=%E5%85%A8%E9%83%A8&hot_id=2'
					},
					{
						title: 'AcFun',
						iconUrl:'https://img.printf520.com/img/142.png',
						url:'https://mo.fish/?class_id=%E5%85%A8%E9%83%A8&hot_id=142'
					},
					{
						title: '知乎推荐',
						iconUrl:'https://img.printf520.com/img/picture/zhihu.com.png',
						url:'https://mo.fish/?class_id=%E5%85%A8%E9%83%A8&hot_id=1053'
						// url:'https://www.zhihu.com/hot'
					},
					{
						title: '抖音',
						iconUrl:'../../static/dy.png',
						url:'https://mo.fish/?class_id=%E5%85%A8%E9%83%A8&hot_id=148'
					},
					{
						title: '什么值得买',
						iconUrl:'../../static/zdm.png',
						url:'https://mo.fish/?class_id=%E5%85%A8%E9%83%A8&hot_id=117'
					},
					{
						title: '观察者',
						iconUrl:'https://img.printf520.com/img/guanchaz.png',
						url:'https://mo.fish/?class_id=%E5%85%A8%E9%83%A8&hot_id=123'
					},
				],
				isShow: false,
				message: 'Hello',
				selectMenuIndex:0,
			}
		},
		computed: {
			btnImgUrl: function() {
				// console.log('执行了 btnImgUrl')
				return this.isShow ? '../../static/show.png' : '../../static/unshow.png'
			},
		},
		components: {
			// MenuList
			SwiperList,
			AllList,
			ListContent
		},
		onLoad() {
			// sayName('小五')

			// console.log('baseUrl_______2',config.baseUrl)
			if(process.env.NODE_ENV === 'development'){
				console.log('开发环境')
			}
			if (process.env.NODE_ENV === 'production') {
				console.log('生产环境')
			}
		},
		methods: {
			switchBtn(){
				this.isShow = !this.isShow
			},
			
			handleOk(msg){
				console.log('msg',msg)
				// this.contentUrl = msg.url;
				this.selectMenuIndex = msg.index;
				// console.log('this.contentUrl---',this.contentUrl)
			}
		},
	}
</script>

<style scoped lang="scss">
	.index-content-tp {
		text-align: center;
	}

	.list-box {
		// position: relative;
		padding: 5px 10px;
		box-sizing: border-box;
		min-height: 30px;
		z-index: 9;

		/* background-color: #f8f8f8; */
		.btn-show {
			position: absolute;
			top: 0;
			right: 0;
			z-index: 10;
			width: 30px;
			text-align: center;
			padding: 10px 0;
			box-sizing: border-box;
			color: #0078ff;
			background-color: #cfd9e0;

			img {
				width: 15px;
				height: 20px;
				vertical-align: middle;
			}
		}
	}
	.list-content{
		position: fixed;
		left: 0;right: 0;;
		margin: auto;
		width: 90%;
		border:3px solid gray;
		box-sizing: border-box;
	}
	.contentHeightA{
		top: 120px;
	}
	.contentHeightB{
		top: 200px;
	}
</style>
