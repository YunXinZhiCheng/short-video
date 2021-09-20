<template>
	<view class="videoPlayer">
		<video id="myVideo" class="video" :controls="false" :loop="true" :src="video.src" @click="click">
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
				// 播放状态
				play: false
			};
		},
		// 生命周期函数
		mounted() {
			this.videoContext = uni.createVideoContext('myVideo', this)
		},
		methods: {
			// 点击事件
			click() {
				if (this.play === false) { // 非播放状态 就让其播放
					this.playCurrent()
				} else { // 播放状态 就让其暂停
					this.pause()
				}
			},
			// 视频播放方法
			player() {
				if (this.play === false) {
					console.log('player播放')
					this.videoContext.seek(0) // 从0开始从头播放
					this.videoContext.play()
					this.play = true
				}
			},
			// 视频暂停方法
			pause() {
				if (this.play === true) {
					console.log('pause暂停')
					this.videoContext.pause()
					this.play = false
				}

			},
			// 当前视频播放
			playCurrent() {
				if (this.play === false) {
					this.videoContext.play()
					this.play = true
				}
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
