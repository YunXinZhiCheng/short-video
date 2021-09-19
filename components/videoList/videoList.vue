<template>
	<view class="videoList">
		<view class="swiper-box">
			<!-- Swiper滑块视图容器: 纵向滑动 -->
			<swiper class="swiper" :vertical="true">
				<swiper-item>
					<view class="swiper-item ">第1页</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item ">第2页</view>
				</swiper-item>
				<swiper-item>
					<view class="swiper-item ">第3页</view>
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

			};
		}
	}
</script>

<style>
.swiper-box {
	height: 100%;
	width: 100%;
}
</style>
