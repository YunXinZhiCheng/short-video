<template>
	<view class="content">
		<!-- 使用first-nav组件 -->
		<first-nav></first-nav>

		<!-- 使用videoList组件
		     组件通讯：父传子 list
		 -->
		<videoList></videoList>

		<!-- 使用tab组件 -->
		<tab></tab>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		onLoad() {
			// 调用网络数据方法
			// this.getVideo()
		},
		methods: {
			// 定义网络数据请求方法
			// getVideo() {
			// 	uni.request({
			// 		// 数据请求地址
			// 		url: 'http://localhost:80/api/videos.json',
			// 		// 数据请求成功后
			// 		success: (res) => {
			// 			console.log(res)
			// 			this.list = res.data.list
			// 		}
			// 	})
			// }
		}
	}
</script>

<style>
	.content {
		width: 100%;
		height: 100%;

	}
</style>
