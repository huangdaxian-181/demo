<template>
	<view class="goods_details">
		<view class="uni-seleton">
			<uni-icons class="back-btn iconfont iconarrow_btn_left" type="arrowleft" color="#fff" @click="navBack" />
		</view>
	</view>
</template>

<script>
</script>

<style scoped lang='scss'>
	.back-btn {
		width: 100%;
		position: absolute;
		z-index: 999;
		padding-top: var(--status-bar-height);
		padding-left: 40upx;
		padding-right: 40upx;
		top: 20upx;
		font-size: 40upx;
		color: #fff;
		display: flex;
		align-items: center;

		.nav-title {
			width: 590upx;
			text-align: center;
		}
	}
</style>
