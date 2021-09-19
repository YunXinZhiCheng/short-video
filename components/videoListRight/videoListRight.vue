<template>
	<view class="videoListRight">
		<!-- 作者头像 -->
		<view class="author-img">
			<image class="img" src="../../static/images/author1.jpg" mode="">
				</imgage>
		</view>
		<!-- 收藏图标 -->
		<view class="iconfont icon-aixin right-box">

		</view>

		<!-- 评论 -->
		<view class="iconfont icon-pinglun right-box">

		</view>
		<!-- 评论数量 -->
		<view class="number">123</view>

		<!-- 分享 -->
		<view class=" iconfont icon-fenxiang right-box">

		</view>
		<!-- 分享数量 -->
		<view class="number">223</view>

		<!-- 动画圆形CD -->
		<view class="round">
			<image class="img" src="../../static/images/roundCD.jpeg" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		// 视频列表右侧图标栏组件
		name: "videoListRight",
		data() {
			return {

			};
		}
	}
</script>

<style>
	/* 右侧图标栏样式 */
	.videoListRight {
		width: 50px;
		margin: 0 auto;
	}

	/* 作者头像样式 */
	.author-img {
		width: 50px;
		height: 50px;
		border-radius: 50%;
		border: 2px solid #FFFFFF;
	}

	/* 图片样式 */
	.img {
		width: 50px;
		height: 50px;
		border-radius: 50%;
	}

	/* 图标字体样式 */
	.right-box {
		width: 50px;
		height: 40px;
		line-height: 40px;
		margin-top: 13px;
		text-align: center;
		color: #FFFFFF;
		font-size: 33px;
	}

	/* 数量 */
	.number {
		font-size: 10px;
		text-align: center;
		color: #FFFFFF;
	}

	/* 圆形CD */
	.round {
		margin-top: 15px;
		animation: rotate 1.5s linear 0.2s infinite;
		width: 50px;
		height: 50px;
	}

	/* 圆形CD 旋转动画 一圈 0到360度  */
	@keyframes rotate {
		0% {
			transform: rotate(0deg);
		}

		100% {
			transform: rotate(360deg);
		}
	}
</style>
