<template>
	<view class="content">
		<page-head :title="title"></page-head>
		<view class="uni-padding-wrap">
			<view class="uni-title uni-common-mt">
				数组类型
				<text>\nnodes属性为Array</text>
			</view>
			<view class="uni-common-mt" style="background:#FFF; padding:20rpx;"><rich-text :nodes="nodes"></rich-text></view>
			<!-- #ifdef H5 -->
			<view class="uni-title uni-common-mt">
				字符串类型
				<text>\nnodes属性为String</text>
			</view>
			<view class="uni-common-mt" style="background:#FFF; padding:20rpx;"><rich-text :nodes="strings"></rich-text></view>
			<!-- #endif -->
		</view>
	</view>
</template>
<script>
export default {
	data() {
		return {
			title: 'rich-text',
			nodes: [ // node 为 Array 类型。nodes 属性推荐使用 Array 类型，由于组件会将 String 类型转换为 Array 类型，所以性能会有所下降
				{
					name: 'div',
					type: 'node', // type 默认为 node, 即元素节点
					attrs: { // attrs 不支持 id，支持 class
						class: 'div_class',
						style: 'line-height: 60px; color: red;'
					},
					children: [
						{
							type: 'text', // type=text, 即文本节点
							text: 'Hello&nbsp;World!'
						},
						{
							type: 'node',
							name: 'img', // img 标签仅支持网络图片
							attrs: {
								style: 'width: 100px;',
								src: 'http://photocdn.sohu.com/20120910/Img352705474.jpg'
							}
						}
					]
				}
			],
			// node 为 String 类型
			strings: '<div style="text-align:center;"><img src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/images/uni@2x.png"/></div>'
		};
	}
};
</script>
