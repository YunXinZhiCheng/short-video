<template>
	<view class="tab">
		<view class="tab-box">
			首页
		</view>
		<view class="tab-box">
			关注
		</view>
		<view class="tab-box">
			<!-- 加号图标 -->
			<view class="iconfont icon-jiahao icon-box ">
			</view>
		</view>

		<view class="tab-box">
			消息
		</view>
		<view class="tab-box">
			我
		</view>
	</view>
</template>

<script>
	export default {
		// 底部tab栏组件
		name: "tab",
		data() {
			return {

			};
		}
	}
</script>

<style>
	/* 推荐使用flex布局 */
	.tab {
		height: 50px;
		width: 100%;
		/* 固定定位，左下角 */
		position: fixed;
		bottom: 0;
		left: 0;
	}

	.tab-box {
		float: left;
		width: 20%;
		color: #FFFFFF;
		background: #000000;
		text-align: center;
		height: 50px;
		line-height: 50px;
		font-size: 20px;
	}

	/* 图标样式 */
	.icon-box {
		width: 60%;
		height: 30px;
		background: #FFFFFF;
		color: #000000;
		margin: 10px 20%;
		line-height: 30px;
		border-radius: 5px;
		font-size: 20px;
	}
</style>
