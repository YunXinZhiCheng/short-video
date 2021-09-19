<template>
	<view class="videoListLeft">
		<!-- 作者+标题+音乐 -->
		<view class="author">作者</view>
		<view class="title">标题</view>
		<view class="music">音乐</view>
	</view>
</template>

<script>
	export default {
		// 视频列表左侧信息栏组件
		name: "videoListLeft",
		data() {
			return {

			};
		}
	}
</script>

<style>
	/* 视频列表左侧信息栏样式 */
	.videoListLeft {
		width: 150px;
		height: 150px;
		margin-left: 10px;
		color: #FFFFFF;
	}

	/* 作者 */
	.author {
		height: 35px;
		line-height: 35px;
		font-size: 15px;
	}

	/* 标题 */
	.title {
		width: 100%;
		word-wrap: break-word;
		line-height: 22px;
		font-size: 12px;
	}

	/* 音乐 */
	.music {
		height: 35px;
		line-height: 35px;
		font-size: 12px;
	}
</style>
