<template>
	<view class="content">
		<view>
			<view v-show="index==0" class="content-item">
				<p>虎扑列表</p>
				<!-- <web-view :webview-styles="webviewStyles" src="https://m.hupu.com/"></web-view> -->
			</view>
			<view v-show="index==1" class="content-item">
				<p>AcFun</p>
			</view>
			<view v-show="index==2" class="content-item">
				<p>知乎推荐</p>
			</view>
			<view v-show="index==3" class="content-item">
				<p>抖音</p>
			</view>
			<view v-show="index==4" class="content-item">
				<p>什么值得买</p>
			</view>
			<view v-show="index==5" class="content-item">
				<p>观察者</p>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: 'listContent',
		data() {
			return {
				// webviewStyles: {
				// 	progress: {
				// 		color: '#FF3333',
				// 		height:'80%'
				// 	},
				// }
			}
		},
		props: {
			index: {
				type: Number,
				default: 0
			}
		}
	}
</script>

<style scoped lang="scss">
	.content {
		min-height: 400px;
		overflow: hidden;
		// background-color: lightblue;

		.content-item {
			p {
				line-height: 2em;
				text-align: center;
			}

			web-view {
				// background-color: lightpink;
			}
		}
	}
</style>
