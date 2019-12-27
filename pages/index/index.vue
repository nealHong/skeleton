<template>
	<view class="content">
		<skeleton :rows="20" :loading="loading" :grid="true" :title="true" :banner="true"></skeleton>
	</view>
</template>

<script>
	import skeleton from "../../components/skeleton.vue"
	export default {
		components:{
			skeleton
		},
		data() {
			return {
				title: 'Hello',
				loading: true
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
		
	}

	
</style>
