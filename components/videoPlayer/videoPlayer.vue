<template>
	<view class="videoPlayer">
		<video id="myVideo" class="video" :controls="false" :loop="true" :src="video.src" controls>
		</video>
	</view>
</template>

<script>
	export default {
		// 视频播放组件
		name: "videoPlayer",
		// 接收属性
		props: ['video'],
		data() {
			return {

			};
		},
		// 生命周期函数
		mounted() {
			this.videoContext = uni.createVideoContext('myVideo', this)
		},
		methods: {
			// 视频播放方法
			player() {
				console.log('player播放')
				this.videoContext.seek(0) // 从0开始从头播放
				this.videoContext.play()
			},
			// 视频暂停方法
			pause() {
				console.log('pause暂停')
				this.videoContext.pause()
			}
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
