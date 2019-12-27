<template>
	<view class="skeleton skeleton--animate" v-if="loading">
		<view class="skeleton__content">
			<view v-if="banner" class="skeleton__banner"></view>
			<block v-if="grid">
				<view class="skeleton__grid">
					<view class="skeleton__grid__item"></view>
					<view class="skeleton__grid__item"></view>
					<view class="skeleton__grid__item"></view>
					<view class="skeleton__grid__item"></view>
				</view>
				<view class="skeleton__grid">
					<view class="skeleton__grid__item"></view>
					<view class="skeleton__grid__item"></view>
					<view class="skeleton__grid__item"></view>
					<view class="skeleton__grid__item"></view>
				</view>
			</block>
			<view v-if="title" class="skeleton__title"></view>
			<view class="skeleton__row" v-for="item in rows" :key="item"></view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			rows: {
				type: Number,
				default: 0
			},
			loading: {
				type: Boolean,
				default: false
			},
			title: {
				type: Boolean,
				default: false
			},
			banner: {
				type: Boolean,
				default: false
			},
			grid: {
				type: Boolean,
				default: false
			}
		}
	}
</script>

<style lang="scss">
	@keyframes skeleton-blink {
		50% {
			opacity: .6
		}
	}

	.skeleton {
		display: flex;
		padding: 32rpx;
		background-color: #FFFFFF;
	}


	.skeleton__content {
		width: 100%;
	}

	.skeleton__banner {
		margin-bottom: 24rpx;
		width: 100%;
		background-color: #f2f3f5;
		height: 300rpx;
		border-radius: 30rpx;
	}
	.skeleton__grid{
		display: flex;
		margin-bottom: 40rpx;
		.skeleton__grid__item{
			flex: 1;
			height: 100rpx;
			margin-right: 30rpx;
			background-color: #f2f3f5;
			&:last-child{
				margin-right: 0;
			}
		}
	}
	.skeleton__row,
	.skeleton__title {
		height: 32rpx;
		background-color: #f2f3f5;
	}

	.skeleton__title {
		width: 40%;
		margin: 0;
	}

	.skeleton__row {
		width: 100%;
	}

	.skeleton__row:not(:first-child) {
		margin-top: 24rpx;
	}

	.skeleton__title+.skeleton__row {
		margin-top: 40rpx;
	}

	.skeleton--animate {
		animation: skeleton-blink 1.2s ease-in-out infinite;
	}
</style>
