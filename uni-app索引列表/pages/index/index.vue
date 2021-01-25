<template>
	<view class="container">

		<!-- 左边内容 -->
		<scroll-view class="scroller" :scroll-into-view="toView" scroll-y scroll-with-animation>
			<view :id="item.text" class="left" v-for="item in list">
				{{item.id}}
				{{item.textCn}}
			</view>
		</scroll-view>

		<!-- 右边索引 -->
		<view>
			<view :data-id="item.text" v-for="item in list" @tap="bindToView">
			{{item.id}}
			{{item.textCn}}
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					{
						id:1,
						textCn:'北京',
						text:'BeiJing'
					},
					{
						id:2,
						textCn:'天津',
						text:'TianJin'
					},
					{
						id:3,
						textCn:'河北',
						text:'HeBei'
					},
					
					{
						id:4,
						textCn:'山西',
						text:'ShanXi'
					},
					{
						id:5,
						textCn:'内蒙古',
						text:'NeiMengGu'
						
					},
					{
						id:6,
						textCn:'辽宁',
						text:'LiaoNing'
					},
					{
						id:7,
						textCn:'吉林',
						text:'JiLin'
					},
					
					{
						id:8,
						textCn:'黑龙江',
						text:'HeiLongJiang'
					},
					{
						id:9,
						textCn:'上海',
						text:'ShangHai'
					},
					{
						id:10,
						textCn:'江苏',
						text:'JiangSu'
					},
					{
						id:11,
						textCn:'浙江',
						text:'ZheJiang'
					},
					{
						id:12,
						textCn:'安徽',
						text:'AnHui'
					},
					
					{
						id:13,
						textCn:'福建',
						text:'FuJian'
					},
					{
						id:14,
						textCn:'江西',
						text:'JiangXi'
					},
					{
						id:15,
						textCn:'山东',
						text:'ShanDong'
					},
					{
						id:16,
						textCn:'河南',
						text:'HeNan'
					},
					{
						id:17,
						textCn:'湖北',
						text:'HuBei'
					},
					{
						id:18,
						textCn:'湖南',
						text:'HuNan'
					},
					
					{
						id:19,
						textCn:'广东',
						text:'GuangDong'
					},
					{
						id:20,
						textCn:'广西',
						text:'GuangXi'
					},
					{
						id:21,
						textCn:'海南',
						text:'HaiNan'
					},
				],
				toView: ''
			}
		},
		methods: {
			bindToView(event) {
				
				var id = event.currentTarget.dataset.id;
				console.log('id---',id);
				this.toView = id;
				this.$forceUpdate()
			}
		}
	}
</script>

<style lang="scss">
	.container {
		width: 100%;
		display: flex;

		scroll-view {
			height: 100vh;

			.left {
				font-size: 50rpx;
				line-height: 150rpx;
			}
		}

		>view {
			position: fixed;
			right: 10rpx;
		}

	}
</style>
