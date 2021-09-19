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
					<view class="left-box">
						<!-- 使用视频左侧信息栏组件 -->
						<videoListLeft></videoListLeft>
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
				// 视频数据,本地路径用require(),网络路径直接填写
				list: [{
					id: 1,
					src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video1.mp4'
				}, {
					id: 2,
					src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video2.mp4'
				}, {
					id: 3,
					src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video3.mp4'
				}, {
					id: 4,
					src: 'https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video4.mp4'
				}],

			};
		},

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
</style>
