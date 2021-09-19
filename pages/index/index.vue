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
				// 本地数据
				list: [{
					"id": 1,
					"src": "",
					"author": "张三",
					"title": "深圳",
					"loveNumber": 123,
					"commentNumber": 222,
					"shareNumber": 333
				}, {
					"id": 2,
					"src": "",
					"author": "李四",
					"title": "深圳地标",
					"loveNumber": 223,
					"commentNumber": 444,
					"shareNumber": 555
				}, {
					"id": 3,
					"src": "",
					"author": "王五",
					"title": "深圳购物",
					"loveNumber": 323,
					"commentNumber": 666,
					"shareNumber": 666
				}, {
					"id": 4,
					"src": "",
					"author": "赵六",
					"title": "深圳建筑",
					"loveNumber": 423,
					"commentNumber": 777,
					"shareNumber": 777
				}]
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
