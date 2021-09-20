<template>
	<view class="city">
		<!-- 使用first-nav组件 -->
		<first-nav></first-nav>

		<!-- 使用cityContent组件 -->
		<cityContent></cityContent>

		<!-- 使用tab组件 -->
		<tab></tab>



	</view>
</template>

<script>
	export default {
		data() {
			return {

			}
		},
		methods: {

		}
	}
</script>

<style>
	/* 城市页面的样式 */
	.city {
		width: 100%;
		height: 100%;
		background: #000000;
	}
</style>
