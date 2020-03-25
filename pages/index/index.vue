<template>
	<view>
		<!-- <view class="uni-tab-bar">
			<scroll-view scroll-x class="uni-swiper-tab">
				<block v-for="(tab,index) in tabBars" :key="tab.id">
					<view class="swiper-tab-list"
					 :class="{'active':tabIndex==index}"
					 @tap="tabtap(index)">
					{{tab.name}}
					<view class="swiper-tab-line"></view>
					</view>
				</block>
			</scroll-view>
		</view> -->
		<swiper-tab-head :tabBars="tabBars" :tabIndex="tabIndex" @tabtap="tabtap"></swiper-tab-head>
		<swiper class="swiper-box"
		 :style="getHeight"
		  :current="tabIndex"
		  @change="tabChange">
			<swiper-item v-for="(items,index) in newslist" :key="index">
				<scroll-view scroll-y class="list">
					<block v-for="(item,index1) in items.list" :key="index1">
						<index-list :item="item" :index="index1"></index-list>
					</block>
				</scroll-view>
			</swiper-item>
		</swiper>
		
		
		
		
		<!-- <block v-for="(item,index) in list" :key="index">
			<index-list :item="item" :index="index"></index-list>
		</block>
		 -->
	</view>
</template>

<script>
	import swiperTabHead from "../../components/index/swiper-tab-head.vue";
	import indexList from "../../components/index/index-list.vue";
	export default {
		onLoad(){
			uni.getSystemInfo({
			    success: (res)=>{
					let height = res.windowHeight - uni.upx2px(100);
					console.log(height);
					this.swiperHeight=height;
			    }
			});
		},
		data() {
			return {
				swiperHeight: 100,
				tabIndex:0,
				tabBars:[
					{name:"关注",id:"guanzhu"},
					{name:"推荐",id:"tuijian"},
					{name:"体育",id:"tiyu"},
					{name:"热点",id:"redian"},
					{name:"财经",id:"caijing"},
					{name:"娱乐",id:"yule"},
				],
				newslist:[
					{
						list:[
							   { userpic:"../../static/demo/userpic/12.jpg",
								username:"昵称",
								isguanzhe:false,
								title:"我是标题",
								type:"img",//img:图文 video:视频
								titlepic:"../../static/demo/datapic/11.jpg",
								infonum:{
									index:2,//0:没有操作 1:ding 2:cai
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
									index:1,//0:没有操作 1:ding 2:cai
									dingnum:11,
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
									index:1,//0:没有操作 1:ding 2:cai
									dingnum:11,
									cainum:11
								},
								commentnum:10,
								sharenum:10
							}
						]
					},
					{
						list:[
							{ userpic:"../../static/demo/userpic/12.jpg",
								username:"昵称",
								isguanzhe:false,
								title:"我是标题",
								type:"img",//img:图文 video:视频
								titlepic:"../../static/demo/datapic/11.jpg",
								infonum:{
									index:2,//0:没有操作 1:ding 2:cai
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
									index:1,//0:没有操作 1:ding 2:cai
									dingnum:11,
									cainum:11
								},
								commentnum:10,
								sharenum:10
							}
						]
					},
					{
						list:[
							{ userpic:"../../static/demo/userpic/12.jpg",
								username:"昵称",
								isguanzhe:false,
								title:"我是标题",
								type:"img",//img:图文 video:视频
								titlepic:"../../static/demo/datapic/11.jpg",
								infonum:{
									index:2,//0:没有操作 1:ding 2:cai
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
									index:1,//0:没有操作 1:ding 2:cai
									dingnum:11,
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
									index:1,//0:没有操作 1:ding 2:cai
									dingnum:11,
									cainum:11
								},
								commentnum:10,
								sharenum:10
							}
						]
					},
					{
						list:[]
					},
					{
						list:[]
					},
					{
						list:[]
					}
				],
			}
		},
		computed:{
			getHeight() {
				// #ifdef MP-ALIPAY
				let height = uni.getSystemInfoSync().windowHeight - uni.upx2px(100) - 44;
				return `height: ${height}px;`;
				// #endif
			}
		},
		methods: {
			tabtap(index){
				console.log(index);
				this.tabIndex=index;
			},
			tabChange(e){
				this.tabIndex = e.detail.current;
			}
		},
		components:{
			indexList,
			swiperTabHead
		},
		
	}
</script>

<style scoped>
	
	/* .swiper-tab-line,.active{
		border-bottom: 6upx solid #fede33;
		width: 70upx;
		margin: auto;
		border-radius: 20upx;
	} */
	.swiper-box{
		height: 700px;
	}
</style>
