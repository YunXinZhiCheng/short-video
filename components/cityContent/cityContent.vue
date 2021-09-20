<template>
	<view class="cityContent">
		<!-- 关联栏 包含左右 -->
		<view class="conlation">
			<!-- 定位图标 -->
			<view class="iconfont icon-dingwei conlation-left ">
				自动定位：深圳
			</view>
			<!-- 切换图标 -->
			<view class="conlation-right">
				切换<text class="iconfont icon-qiehuan"></text>
			</view>
		</view>

		<!-- 列表栏  视频列表-->
		<view class="videoList">
			<!-- 列表项1 -->
			<view class="item">
				<!-- 视频 -->
				<view class="video">
					<video style="width: 100%;height: 100%;"
						src="https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video1.mp4"></video>
				</view>
				<!-- 头像 -->
				<view class="img">
					<image class="image-box" src="../../static/images/author1.jpg"></image>
				</view>
			</view>
			<!-- 列表项2 -->
			<view class="item">
				<!-- 视频 -->
				<view class="video">
					<video style="width: 100%;height: 100%;"
						src="https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video2.mp4"></video>
				</view>
				<!-- 头像 -->
				<view class="img">
					<image class="image-box" src="../../static/images/author2.jpg"></image>
				</view>
			</view>
			<!-- 列表项3 -->
			<view class="item">
				<!-- 视频 -->
				<view class="video">
					<video style="width: 100%;height: 100%;"
						src="https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video3.mp4"></video>
				</view>
				<!-- 头像 -->
				<view class="img">
					<image class="image-box" src="../../static/images/author3.jpg"></image>
				</view>
			</view>
			<!-- 列表项4 -->
			<view class="item">
				<!-- 视频 -->
				<view class="video">
					<video style="width: 100%;height: 100%;"
						src="https://luoyuancheng-1303025190.cos.ap-hongkong.myqcloud.com/shortvideo/video4.mp4"></video>
				</view>
				<!-- 头像 -->
				<view class="img">
					<image class="image-box" src="../../static/images/author4.jpg"></image>
				</view>
			</view>

		</view>
	</view>
</template>

<script>
	export default {
		// 城市内容组件
		name: "cityContent",
		data() {
			return {

			};
		}
	}
</script>

<style>
	/* 城市内容的样式 */
	.cityContent {
		width: 100%;
		background: #000000;
	}

	/* 城市定位 */
	.conlation {
		width: 100%;
		height: 40px;
		padding-top: 70px;
		overflow: hidden;
		color: #AAAAAA;
	}

	/* 左侧定位 */
	.conlation-left {
		float: left;
		font-size: 13px;
		padding-left: 15px;

	}

	/* 右侧切换 */
	.conlation-right {
		float: right;
		font-size: 13px;
		padding-right: 15px;

	}

	/* 视频列表 */
	.videoList {
		width: 100%;
		overflow: hidden;
		background: #000000;
	}

	/* 视频列表项 */
	.item {
		width: 50%;
		float: left;
		position: relative;
	}

	/* 视频 */
	.video {
		width: 92%;
		height: 300px;
		margin-left: 4px;
		z-index: 18;
	}

	/* 头像 */
	.img {
		position: absolute;
		bottom: 7px;
		right: 15px;
	}

	.image-box {
		width: 30px;
		height: 30px;
		border-radius: 50%;
	}
</style>
