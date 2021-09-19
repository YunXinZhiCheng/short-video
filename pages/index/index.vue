<template>
	<view class="content">
		<!-- 使用first-nav组件 -->
		<first-nav></first-nav>

		<!-- 使用videoList组件 -->
		<videoList></videoList>

		<!-- 使用tab组件 -->
		<tab></tab>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello'
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		width: 100%;
		height: 100%;

	}
</style>
