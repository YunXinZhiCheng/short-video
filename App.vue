<script>
	export default {
		onLaunch: function() {
			console.log('App Launch')
			// 隐藏tabBar
			uni.hideTabBar({
				
			})
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
	/* iconfont.css */
@import url("static/lib/fonts/iconfont.css");

html,body {
	width: 100%;
	height: 100%;
}
</style>
