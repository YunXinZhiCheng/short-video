<template>
	<view class="videoListRight">
		<!-- 作者头像 -->
		<view class="author-img">
			<image class="img" :src="item.authorImg" mode="">
				</imgage>
				<!-- 关注图标
					事件：点击后隐藏图标
					指令：v-show 优先使用
				 -->
				<view class="iconfont icon-jiahao add" v-show="show" @click="hidden"></view>
		</view>
		<!-- 收藏图标 爱心
		     事件：点击收藏会改变颜色
		 -->
		<view class="iconfont icon-aixin right-box" :style="{ color: initColor }" @click="changeColor"></view>
		<!-- 收藏数量 -->
		<view class="number">{{item.loveNumber}}</view>

		<!-- 评论 -->
		<view class="iconfont icon-pinglun right-box"></view>
		<!-- 评论数量 -->
		<view class="number">{{item.commentNumber}}</view>

		<!-- 分享 -->
		<view class=" iconfont icon-fenxiang right-box"></view>
		<!-- 分享数量 -->
		<view class="number">{{item.shareNumber}}</view>

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
		props: ['item'],
		data() {
			return {
				show: true, // 显示与隐藏
				initColor: 'white' // 默认颜色
			};
		},
		methods: {
			// 关注：隐藏事件
			hidden() {
				// console.log('hidden隐藏')
				this.show = false

			},
			// 收藏：改变颜色事件,三元运算符判断
			changeColor() {
				// console.log('change颜色')
				this.initColor = this.initColor === 'white' ? 'red' : 'white'
			},
			// 点赞：改变颜色事件
			change() {
				this.initColor = "red"
			}
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
		/* 相对定位，为了关注图标 */
		position: relative;
	}

	/* 图片样式 */
	.img {
		width: 50px;
		height: 50px;
		border-radius: 50%;
	}

	/* 关注加号图标样式 */
	.add {
		width: 18px;
		height: 18px;
		border-radius: 50%;
		background: red;
		/* 绝对定位: 向上与向左移动 */
		position: absolute;
		bottom: -9px;
		left: 16px;
		/* 水平与垂直居中 */
		text-align: center;
		line-height: 18px;
		/* 图标字体 */
		color: #FFFFFF;
		font-size: 10px;
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
