<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	.list-item {
		display: inline-block;
		margin-right: 10px;
		font-size: 25rpx;
		padding: 5px 15px;
		box-sizing: border-box;
		border-radius: 15px;
		background-color: rgb(246, 246, 246);
	}
	.icon-img{
		margin-right: 5px;
		vertical-align: middle;
		width: 15px;
	}
</style>
