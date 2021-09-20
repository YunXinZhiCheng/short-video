<template>
	<view class="videoList">
		<view class="swiper-box">
			<!-- Swiper滑块视图容器: 
				属性：纵向滑动 :vertical
				事件：改变触发 @change
				事件：手指开始触摸触发 @touchstart
				事件：手指结束触摸触发 @touchend
			 -->
			<swiper class="swiper" :vertical="true" @change="change" @touchstart="touchStart" @touchend="touchEnd">
				<swiper-item v-for="item in list" :key="item.id">
					<view class="swiper-item " style="color: #000000;">
						<!-- 使用视频播放组件
						     父传子：绑定属性
							 子传父：自定义事件
						 -->
						<videoPlayer :video="item" ref="player" @changeClick="changeClick"></videoPlayer>
					</view>
					<view class="left-box">
						<!-- 使用视频列表左侧信息栏组件 -->
						<videoListLeft></videoListLeft>
					</view>
					<view class="right-box">
						<!-- 使用视频列表右侧图标栏组件 -->
						<videoListRight ref="right"></videoListRight>
					</view>
				</swiper-item>
			</swiper>
		</view>


	</view>
</template>

<script>
	// 定义一个定时器
	var time = null

	export default {
		// 视频列表组件
		name: "videoList",
		data() {
			return {
				// 视频数据,本地路径用require(),网络路径直接填写
				list: [{
						id: 1,
						src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video1.mp4'
					}, {
						id: 2,
						src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video2.mp4'
					},
					{
						id: 3,
						src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video3.mp4'
					},
					{
						id: 4,
						src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video4.mp4'
					}
				],

				// 页面开始与结束纵向距离
				pageStartY: 0,
				pageEndY: 0,
				// 页面初始索引
				page: 0

			};
		},

		methods: {
			// 改变事件 双击
			changeClick() {
				console.log('子传父666')
				// 点赞操作，调用子组件方法videoListRight
				this.$refs.right[0].change()

			},
			// 改变事件
			change(res) {
				// 移除定时器
				clearTimeout(time)

				// 当前视频索引 current从0开始
				console.log(res.detail.current)
				this.page = res.detail.current

				// 设置定时器
				time = setTimeout(() => {
					// 判断是向上还是向下滑动
					if (this.pageStartY < this.pageEndY) {
						console.log('向下滑动')

						// 获取DOM节点内容 $refs
						this.$refs.player[this.page].player() // 播放当前视频
						this.$refs.player[this.page + 1].pause() // 暂停下一个视频

						// 滑动之后清空距离
						this.pageStartY = 0
						this.pageEndY = 0
					} else {
						console.log('向上滑动')

						// 获取DOM节点内容 $refs
						this.$refs.player[this.page].player() // 播放当前视频
						this.$refs.player[this.page - 1].pause() // 暂停上一个视频

						// 滑动之后清空距离
						this.pageStartY = 0
						this.pageEndY = 0
					}
				}, 100)

			},
			// 开始触摸事件
			touchStart(res) {
				// console.log(res)
				this.pageStartY = res.changedTouches[0].pageY // 赋值给开始触摸纵向距离
				// console.log(this.pageStartY)


			},
			// 结束触摸事件
			touchEnd(res) {
				// console.log(res)
				this.pageEndY = res.changedTouches[0].pageY // 赋值给结束触摸纵向距离
				// console.log(this.pageEndY)
			}
		}

	}
</script>

<style>
	.videoList {
		width: 100%;
		height: 100vh;

	}

	.swiper-box {
		width: 100%;
		height: 100vh;
	}

	.swiper {
		width: 100%;
		height: 100vh;
	}

	.swiper-item {
		width: 100%;
		height: 100vh;
		/* 层级 */
		z-index: 19;
	}

	/* 左侧信息栏样式 */
	.left-box {
		/* 层级 */
		z-index: 20;
		/* 定位 */
		position: absolute;
		left: 10px;
		bottom: 50px;
		color: #FFFFFF;
	}

	/* 右侧图标栏样式 */
	.right-box {
		/* 层级 */
		z-index: 20;
		/* 定位 */
		position: absolute;
		right: 10px;
		bottom: 50px;
		color: #FFFFFF;
	}
</style>
