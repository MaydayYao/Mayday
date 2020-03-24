<template>
	<view>
		<block v-for="(item,index) in list" :key="index">
			<view class="index-list">
				<view class="index-list1 u-f-ac">
					<view class="u-f-ac">
						<image :src="item.userpic"
						 mode="widthFix"
						 lazy-load></image>
						 {{item.username}}
					</view>
					<view class="u-f-ac" v-show="item.isguanzhe">
						<view class="icon iconfont icon-zengjia"></view>关注
					</view>
				</view>
				<view class="index-list2">{{item.title}}</view>
				<view class="index-list3 u-f-ajc">
					<!-- 图片 -->
					<image :src="item.titlepic" mode="widthFix" lazy-load></image>
					<!-- 视频 -->
					<template v-if="item.type=='video'">
						<view class="index-list-play icon iconfont icon-course"></view>
						<view class="index-list-playinfo">
							{{item.playnumm}} {{item.long}}
						</view>
					</template>
				</view>
				<view class="index-list4 u-f-ajc">
					<view class="u-f-ac">
						<view class="icon iconfont icon-dianzan1" 
						:class="{'active':(item.infonum.index==1)}"></view>
						<view>{{item.infonum.dingnum}}</view>
						<view class="icon iconfont icon-cai"
						:class="{'active':(item.infonum.index==2)}"></view>
						<view>{{item.infonum.cainum}}</view>
					</view>
					<view class="u-f-ac">
						<view class="icon iconfont icon-conversation_icon"></view>
						<view>{{item.commentnum}}</view>
						<view class="icon iconfont icon-fenxiang"></view>
						<view>{{item.sharenum}}</view>
					</view>
				</view>
			</view>
		</block>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[
					{
						userpic:"../../static/demo/userpic/12.jpg",
						username:"昵称",
						isguanzhe:false,
						title:"我是标题",
						type:"img",//img:图文 video:视频
						titlepic:"../../static/demo/datapic/11.jpg",
						infonum:{
							index:1,//0:没有操作 1:ding 2:cai
							dingnum:20,
							cainum:11
						},
						commentnum:10,
						sharenum:10
					},
					{
						userpic:"../../static/demo/userpic/12.jpg",
						username:"昵称",
						isguanzhe:true,
						title:"我是标题",
						type:"video",//img:图文 video:视频
						titlepic:"../../static/demo/datapic/11.jpg",
						playnumm:"20w",
						long:"2:47",
						infonum:{
							index:2,//0:没有操作 1:ding 2:cai
							dingnum:11,
							cainum:11
						},
						commentnum:10,
						sharenum:10
					}
				]
			}
		},
		computed:{
		},
		methods: {

		}
	}
</script>

<style scoped>
	
	.index-list{
		padding: 20upx;
		border-bottom: 1upx solid;
	}
	.index-list1{
		justify-content: space-between;
	}
	.index-list1>view:first-child{
		align-items: center;
	}
	.index-list1>view:first-child image{
		width:90upx;
		height: 90upx;
		border-radius: 100%;
	}
	.index-list1>view:last-child{
		
	}
	.index-list1>view:last-child{
		background: #999;
		border-radius: 5upx;
	}
	.index-list2{
		padding-top: 15upx;
	}
	.index-list3{
		position: relative;
		padding-top: 15upx;
	}
	.index-list3>image{
		width: 100%;
		border-radius: 20upx;
	}
	.index-list4{
		padding: 15upx 0;
	}
	.index-list4 view{
		color: #999;
	}
	.index-list4 .active,.index-list4 .active>view{
		color: #ff9619;
	}
	.index-list4>view>view{
		margin-left: 20upx;
	}
	.icon{
		font-size: 40upx;
	}
	.index-list-play{
		position: absolute;
		left: 250upx;
	}
	.index-list-playinfo{
		position: absolute;
		background: rgba(51,51,51,0.72);
		color: #fff;
		bottom: 10upx;
		left: 500upx;
		border-radius: 40upx;
		font-size: 20upx;
		padding: 0 10upx;
	}
	.icon-course{
		font-size: 200upx;
		color: #fff;
		
	}
</style>
