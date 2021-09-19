<template>
	<view class="videoPlayer">
		<video class="video" :controls="false" :loop="true" :src="video.src" controls
			object-fit="contain">
		</video>
	</view>
</template>

<script>
	export default {
		// 视频播放组件
		name: "videoPlayer",
		// 接收属性
		props:['video'],
		data() {
			return {

			};
		}
	}
</script>

<style>
	.videoPlayer {
		width: 100%;
		height: 100%;
	}

	.video {
		width: 100%;
		height: 100%;
	}
</style>
