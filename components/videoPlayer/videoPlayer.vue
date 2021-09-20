<template>
	<view class="videoPlayer">
		<video id="myVideo" class="video" :controls="false" :loop="true" :src="video.src" @click="click">
		</video>
	</view>
</template>

<script>
	// 定义一个定时器
	var timer = null

	export default {
		// 视频播放组件
		name: "videoPlayer",
		// 接收属性
		props: ['video'],
		data() {
			return {
				// 播放状态
				play: false,
				// 双击
				dbClick: false
			};
		},
		// 生命周期函数
		mounted() {
			this.videoContext = uni.createVideoContext('myVideo', this)
		},
		methods: {
			// 点击事件
			click() {
				// 移出定时器
				clearTimeout(timer)
				this.dbClick = !this.dbClick
				timer = setTimeout(() => {
					if (this.dbClick) {
						// 单击
						if (this.play === false) { // 非播放状态 就让其播放
							this.playCurrent()
						} else { // 播放状态 就让其暂停
							this.pause()
						}
					} else {
						// 双击
						console.log('双击666')
						// 子传父
						this.$emit('changeClick')
					}
					// 重置点击状态
					this.dbClick = false

				}, 300)

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
