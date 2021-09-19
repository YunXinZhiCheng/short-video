<template>
	<view class="videoList">
		<view class="swiper-box">
			<!-- Swiper滑块视图容器: 纵向滑动 -->
			<swiper class="swiper" :vertical="true">
				<swiper-item v-for="item in list" :key="item.id">
					<view class="swiper-item " style="color: #000000;">
						<!-- 使用视频播放组件 -->
						<videoPlayer :video="item"></videoPlayer>
					</view>
				</swiper-item>
			</swiper>
		</view>


	</view>
</template>

<script>
	export default {
		// 视频列表组件
		name: "videoList",
		data() {
			return {
				// 视频数据
				list: [{
					id: 1,
					src: require('static/video/video1.mp4')
				}, {
					id: 2,
					src: require('static/video/video2.mp4')
				}, {
					id: 3,
					src: require('static/video/video3.mp4')
				}]
			};
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
</style>
