<template>
	<view class="videoListLeft">
		<!-- 作者+标题+音乐 -->
		<view class="author">{{item.author}}</view>
		<view class="title">{{item.title}}</view>
		<view class="box">
			<view class="music">
				@Hello fans Are You Ok?
			</view>
		</view>

	</view>
</template>

<script>
	export default {
		// 视频列表左侧信息栏组件
		name: "videoListLeft",
		props: ['item'],
		data() {
			return {

			};
		}
	}
</script>

<style>
	/* 视频列表左侧信息栏样式 */
	.videoListLeft {
		width: 150px;
		height: 150px;
		margin-left: 10px;
		color: #FFFFFF;
	}

	/* 作者 */
	.author {
		height: 35px;
		line-height: 35px;
		font-size: 15px;
	}

	/* 标题 */
	.title {
		width: 100%;
		word-wrap: break-word;
		line-height: 22px;
		font-size: 12px;
	}

	/* 音乐盒子 */
	.box {
		width: 100px;
		/* 内容超出盒子大小就隐藏 */
		overflow: hidden;
	}

	/* 音乐 */
	.music {
		width: 150px;
		height: 35px;
		line-height: 35px;
		font-size: 12px;
		animation: music 4s linear 0.2s infinite;
	}

	/* 音乐 滚动动画: 水平移动,x轴 */
	@keyframes music {
		0% {
			transform: translate3d(80%, 0, 0);
		}

		100% {
			transform: translate3d(-80%, 0, 0);
		}
	}
</style>
