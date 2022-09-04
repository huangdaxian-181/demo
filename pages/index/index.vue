<template>
	<view class="content">
		<view class="search">
			<uni-search-bar class="uni-mt-10" radius="10" placeholder="搜索单品" clearButton="none" cancelButton="none"
				@confirm="search" />
			<uni-icons class="uni-mt-11" type="color-filled" size="30"></uni-icons>
		</view>

		<view class="list-item">
			<view class="nav">
				<!-- 选项卡水平方向滑动，scroll-with-animation是滑动到下一个选项时，有一个延时效果 -->
				<scroll-view class="tab-scroll" scroll-x="true" scroll-with-animation :scroll-left="scrollLeft">
					<view class="tab-scroll_box">
						<!-- 选项卡类别列表 -->
						<view class="tab-scroll_item" v-for=" (item,index) in category" :key="index"
							:class="{'active':isActive==index}" @click="chenked(index)">
							{{item.name}}
						</view>
					</view>
				</scroll-view>
			</view>
			<!-- 选项卡内容轮播滑动显示，current为当前第几个swiper子项 -->
			<swiper @change="change" :current="isActive" class="swiper-content" :style="fullHeight">
				<swiper-item class="swiperitem-content">
					<scroll-view scroll-y style="height: 85%;">
						<view class="row2">
							
						</view>
						<view class="nav_item">
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/prod_NIKEOUTLETS_DIP-0jal2800005hq73bfdbc_UNEX_DN1771-104-列表图-1.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   Jordan Luka 1 PF
								   男子篮球鞋
							   </view>
							   
							   <view class="nav_item_list_good">
							   	   白 库存30件
							   </view>
							   
							   <view class="nav_item_list_good">
							   	   ¥2
							   </view>
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
                               <view class="nav_item_list_img">
                               	    <img src="/static/hm-goods-card/images/img_25335_0_1.png" alt="" srcset="">
                               </view>
							   <view class="nav_item_list_title">
								   【未来家】高科技凳子治疗腰痛腿痛
								   高科技凳子治疗腰痛腿痛
								   高科技凳子治疗腰痛腿痛
							   </view>
							   
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/18825531_41228356_600.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
							   	未来家】高科技凳子治疗腰痛腿痛
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/18544108_41206463_600.jpg" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
							   	未来家】高科技凳子治疗腰痛腿痛
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/prod_NIKEOUTLETS_DIP-07ig2800g3que45gh7bc_UNEX_DH4071-004-列表图-1.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   Nike Air Zoom Pegasus 39
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/prod_NIKEOUTLETS_DIP-g3k9l9000s2m1mnn72bc_UNEX_DV1229-111-列表图-1.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   Nike Air Force 1 '07 LV8

							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
						</view>
						
						<view class="rows">
							
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiperitem-content">
					<scroll-view scroll-y style="height: 100%;">
						<view class="nav_item">
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/hm-goods-card/images/img_25335_0_1.png" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   【未来家】高科技凳子治疗腰痛腿痛
								   高科技凳子治疗腰痛腿痛
								   高科技凳子治疗腰痛腿痛
							   </view>
							   
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/18825531_41228356_600.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
							   	未来家】高科技凳子治疗腰痛腿痛
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/18544108_41206463_600.jpg" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
							   	未来家】高科技凳子治疗腰痛腿痛
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/prod_NIKEOUTLETS_DIP-07ig2800g3que45gh7bc_UNEX_DH4071-004-列表图-1.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   Nike Air Zoom Pegasus 39
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
							
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/prod_NIKEOUTLETS_DIP-g3k9l9000s2m1mnn72bc_UNEX_DV1229-111-列表图-1.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   Nike Air Force 1 '07 LV8
							
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiperitem-content">
					<scroll-view scroll-y style="height: 100%;">
						<view class="nav_item">
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/prod_NIKEOUTLETS_DIP-g3k9l9000s2m1mnn72bc_UNEX_DV1229-111-列表图-1.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   Nike Air Force 1 '07 LV8
							
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiperitem-content">
					<scroll-view scroll-y style="height: 100%;">
						<view class="nav_item">
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/prod_NIKEOUTLETS_DIP-g3k9l9000s2m1mnn72bc_UNEX_DV1229-111-列表图-1.webp" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
								   Nike Air Force 1 '07 LV8
							
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiperitem-content">
					<scroll-view scroll-y style="height: 100%;">
						<view class="nav_item">
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/18544108_41206463_600.jpg" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
							   	未来家】高科技凳子治疗腰痛腿痛
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
				<swiper-item class="swiperitem-content">
					<scroll-view scroll-y style="height: 100%;">
						<view class="nav_item">
							<view class="nav_item_list">
							   <view class="nav_item_list_img">
							   	    <img src="/static/shi/18544108_41206463_600.jpg" alt="" srcset="">
							   </view>
							   <view class="nav_item_list_title">
							   	未来家】高科技凳子治疗腰痛腿痛
							   </view>
							   <view class="nav_item_list_good">
							   	   黑 库存30件
							   </view>
							   <view class="nav_item_list_good">
							   	   ¥900
							   </view>
							   
							   <view class="nav_item_list_a">
							   	 <img src="static/shi/购物车.png" alt="" srcset="">
							   </view>
							</view>
						</view>
					</scroll-view>
				</swiper-item>
			</swiper>
		</view>

	</view>
</template>

<script>
	export default {
		components: {

		},
		watch: {
			// swiper与上面选项卡联动
			currentindex(newval) {
				this.isActive = newval;
				this.scrollLeft = 0;
				// 滑动swiper后，每个选项距离其父元素最左侧的距离
				for (let i = 0; i < newval - 1; i++) {
					this.scrollLeft += this.category[i].width
				};
			},
		},
		data() {
			return {
				isActive: 0,
				index: 0,
				currentindex: 0,

				category: [{
						id: 1,
						name: '推荐',
					},
					{
						id: 2,
						name: '酒饮',
					},
					{
						id: 3,
						name: '艺术',
					},
					{
						id: 4,
						name: '女装',
					},
					{
						id: 5,
						name: '出行',
					},
					{
						id: 6,
						name: '家电',
					},
					{
						id: 7,
						name: '美妆'
					}
				],
				contentScrollW: 0, // 导航区宽度
				scrollLeft: 0, // 横向滚动条位置
				fullHeight: "",
				dynamicList: [],
				list: [{
						url: 'static/logo.png',
						text: 'Grid 1',
						badge: '0',
						type: "primary"
					},
					{
						url: 'static/logo.png',
						text: 'Grid 1',
						badge: '0',
						type: "primary"
					}, {
						url: 'static/logo.png',
						text: 'Grid 1',
						badge: '0',
						type: "primary"
					}, {
						url: 'static/logo.png',
						text: 'Grid 1',
						badge: '0',
						type: "primary"
					},
				]
			}
		},
		mounted() {
			var that = this;
			//获取手机屏幕的高度，让其等于swiper的高度，从而使屏幕充满
			uni.getSystemInfo({
				success: function(res) {
					that.fullHeight = "height:" + res.windowHeight + "px";
				}
			});
			// 获取标题区域宽度，和每个子元素节点的宽度
			this.getScrollW()
		},
		methods: {
			// 获取标题区域宽度，和每个子元素节点的宽度以及元素距离左边栏的距离
			getScrollW() {
				const query = uni.createSelectorQuery().in(this);
				query.select('.tab-scroll').boundingClientRect(data => {
					// 拿到 scroll-view 组件宽度
					this.contentScrollW = data.width
				}).exec();
				query.selectAll('.tab-scroll_item').boundingClientRect(data => {
					let dataLen = data.length;
					for (let i = 0; i < dataLen; i++) {
						//  scroll-view 子元素组件距离左边栏的距离
						this.category[i].left = data[i].left;
						//  scroll-view 子元素组件宽度
						this.category[i].width = data[i].width
					}
				}).exec()
			},
			onClick: function(e) {
				console.log('onClick');
			},
			// 当前点击子元素靠左留一个选项展示，子元素宽度不相同也可实现
			chenked(index) {
				this.isActive = index;
				this.scrollLeft = 0;
				for (let i = 0; i < index - 1; i++) {
					this.scrollLeft += this.category[i].width
				};
			},
			// swiper滑动时，获取其索引，也就是第几个
			change(e) {
				const {
					current
				} = e.detail;
				this.currentindex = current;
			},
		}
	}
</script>

<style lang="scss">
	// .contents {
	// 	display: flex;
	// 	flex-direction: column;
	// 	align-items: center;
	// 	justify-content: center;
	// }

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}

	.search {
		width: 100%;
		height: 8%;
		display: flex;
	}

	.uni-mt-10 {
		width: 85%;
		float: left;
		display: flex;
	}

	.uni-mt-11 {
		float: left;
		margin-top: 13px;
	}

	.list-item {
		width: 100%;
		height: 90%;
	}

	.content {
		flex-direction: column;
		overflow: hidden;
		height: 90%;
		position: fixed;
		left: 0;
		right: 0;
	}

	page {
		height: 90%;
		display: flex;
		background-color: #FFFFFF;
	}

	.nav {
		border-top: 1rpx solid #f2f2f2;
		background-color: #ffffff;
		position: fixed;
		z-index: 99;
		width: 100%;
		align-items: center;
		height: 100rpx;

		.tab-scroll {
			flex: 1;
			overflow: hidden;
			box-sizing: border-box;
			padding-left: 30rpx;
			padding-right: 30rpx;

			.tab-scroll_box {
				display: flex;
				align-items: center;
				flex-wrap: nowrap;
				box-sizing: border-box;

				.tab-scroll_item {
					line-height: 60rpx;
					margin-right: 29px;
					flex-shrink: 0;
					padding-bottom: 10px;
					display: flex;
					justify-content: center;
					font-size: 14px;
					padding-top: 10px;
				}
			}
		}
	}

	.swiper-content {
		padding-top: 45px;
		flex: 1;
		

		.swiperitem-content {
			background-color: #ffffff;

			.nav_item {
				background-color: #FFFFFF;
				margin-top: 10px;
				width: 100%;
			}
		}
	}

	.active {
		position: relative;
		color: black;
		font-weight: 700;
		font-family: 'Courier New', Courier, monospace;
	}

	.active::after {
		content: "";
		position: absolute;
		width: 130rpx;
		height: 4rpx;
		left: 0px;
		right: 0px;
		bottom: 0px;
		margin: auto;
	}

	/* 隐藏滚动条，但依旧具备可以滚动的功能 */
	/deep/.uni-scroll-view::-webkit-scrollbar {
		display: none
	}


	.nav_item_list {
		height: 160px;
		width: 95%;
		margin: 0 auto;
		// display: flex;
		// align-items: flex-start;
		// flex-direction: column;
		border-radius: 20px;
        box-shadow: 0px 10px 30px rgb(168,168,168);
		background-color: #ffffff;
		margin-top: 10px;
		
	}
	.nav_item_list_img{
		width: 140px;
		height: 130px;
		float: left;
		padding-left: 20px;
		padding-top: 15px;
	}
	.nav_item_list_img img{
		width: 100%;
		height: 100%;
		border-radius: 20px;
		background-color: #EDF0F4;
	}
	.nav_item_list_title{
		width: 40%;
		height: 25%;
		float: left;
		padding-left: 10px;
		padding-top: 30px;
		font-size: 14px;
		overflow: hidden;
		text-overflow: ellipsis;
		display: -webkit-box;
		-webkit-line-clamp: 2;
		-webkit-box-orient: vertical;
	}
	
	.nav_item_list_good{
		width: 30%;
		font-size: 14px;
		float: left;
		padding-left: 10px;
		margin-top: 10px;
		color: #757575;
	}
	
	.nav_item_list_a{
		width: 5%;
		float: right;
		padding-right: 30px;
	}
	
	.rows{
		height: 30px;
	}
	.row2{
		height: 10px;
	}
</style>
