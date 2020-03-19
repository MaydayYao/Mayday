<template>
	<view>
		<view class="index-list">
			<view class="index-list1">
				<view>
					<image src="/static/demo/userpic/12.jpg"
					 mode="widthFix" lazy-load></image>
					 昵称
				</view>
				<view>
					<view class="icon iconfont icon-bianji"></view>关注1
				</view>
			</view>
			<view class="index-list2">我是标题</view>
			<view class="index-list3">
				<image src="../../static/demo/datapic/11.jpg" mode="widthFix" lazy-load></image>
			</view>
			<view class="index-list4">
				<view>
					<view class="icon"></view><view>10</view>
					<view class="icon"></view><view>20</view>
				</view>
				<view></view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		computed:{
		},
		methods: {

		}
	}
</script>

<style>
	.index-list{
		padding: 20upx;
		border-bottom: 1upx solid #EEEEEE;
	}
	.index-list1>view:first-child{
		color: #999999;
	}
	.index-list1>view:first-child image{
		width: 85upx;
		height: 85upx;
		border-radius: 100%;
		margin-right: 10upx;
	}
	.index-list1>view:last-child{
		background: #F4F4F4;
		border-radius:5upx;
		padding: 0 10upx;
	}
	.index-list2{
		padding-top: 15upx;
		font-size: 32upx;
	}
	.index-list3{
		position: relative;
		padding-top: 15upx;
	}
	.index-list3>image{
		width: 100%;
		border-radius: 20upx;
	}
	.index-list4 view{
		color: #999999;
	}
	.index-list4{
		padding: 15upx 0;
	}
	.index-list4>view>view>view,.index-list4>view>view:first-child{
		margin-right: 10upx;
	}
	.index-list-play{
		position: absolute;
		font-size: 140upx;
		color: #FFFFFF;
	}
	.index-list-playinfo{
		position: absolute;
		background: rgba(51, 51, 51, 0.72);
		color: #FFFFFF;
		bottom: 8upx;
		right: 8upx;
		border-radius: 40upx;
		font-size: 22upx;
		padding: 0 12upx;
	}
	.index-list4 .active,.index-list4 .active>view{
		color: #C5F61C;
	}
</style>
