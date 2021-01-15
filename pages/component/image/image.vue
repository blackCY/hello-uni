<template>
	<view>
		<page-head :title="title"></page-head>
		<view class="uni-padding-wrap uni-common-mt">
			<view class="uni-title">
				示例1
				<text>\n本地图片</text>
			</view>
			<view class="uni-center" style="background:#FFFFFF; font-size:0;">
				<!-- #ifdef MP-ALIPAY -->
				<image class="image" mode="widthFix" src="../../../static/uni.png" />
				<!-- #endif -->
				<!-- #ifndef MP-ALIPAY -->
				<image class="image" mode="widthFix" src="../../../static/uni.png" />
				<!-- #endif -->
			</view>
			<view class="uni-title uni-common-mt">
				示例2
				<text>\n网络图片</text>
			</view>
			<view class="uni-center" style="background:#FFFFFF; font-size:0;">
				<image class="image" mode="widthFix" src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png" />
			</view>
		</view>
		<view class="page">
			<view class="image-list">
				<view class="image-item" v-for="(item, index) in array" :key="index">
					<view class="image-content"><image style="width: 200px; height: 200px; background-color: #eeeeee;" :mode="item.mode" :src="src" @error="imageError"></image></view>
					<view class="image-title">{{ item.text }}</view>
				</view>
			</view>
		</view>
	</view>
</template>
<script>
export default {
	data() {
		return {
			title: 'image',
			// mode 有 13 种模式，其中 4 种是缩放模式，9 种是裁剪模式。
			array: [
				{
					mode: 'scaleToFill',
					text: 'scaleToFill：不保持纵横比缩放图片，使图片完全适应'
				},
				{
					mode: 'aspectFit',
					text: 'aspectFit：保持纵横比缩放图片，使图片的长边能完全显示出来'
				},
				{
					mode: 'aspectFill',
					text: 'aspectFill：保持纵横比缩放图片，只保证图片的短边能完全显示出来'
				},
				{
					mode: 'top',
					text: 'top：不缩放图片，只显示图片的顶部区域'
				},
				{
					mode: 'bottom',
					text: 'bottom：不缩放图片，只显示图片的底部区域'
				},
				{
					mode: 'center',
					text: 'center：不缩放图片，只显示图片的中间区域'
				},
				{
					mode: 'left',
					text: 'left：不缩放图片，只显示图片的左边区域'
				},
				{
					mode: 'right',
					text: 'right：不缩放图片，只显示图片的右边边区域'
				},
				{
					mode: 'top left',
					text: 'top left：不缩放图片，只显示图片的左上边区域'
				},
				{
					mode: 'top right',
					text: 'top right：不缩放图片，只显示图片的右上边区域'
				},
				{
					mode: 'bottom left',
					text: 'bottom left：不缩放图片，只显示图片的左下边区域'
				},
				{
					mode: 'bottom right',
					text: 'bottom right：不缩放图片，只显示图片的右下边区域'
				}
			],
			src: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/6acec660-4f31-11eb-a16f-5b3e54966275.jpg'
		};
	},
	methods: {
		imageError: function(e) {
			console.error('image发生error事件，携带值为' + e.detail.errMsg);
		}
	}
};
</script>
<style>
.image {
	margin: 40rpx 0;
	width: 200rpx;
}
</style>
