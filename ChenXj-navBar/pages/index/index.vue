<template>
	<view class="content">
		<view class="nuter">
			<navBar @currentIndex="setIndex" :currentI="thisindex" :scrollChange="scrollChange"></navBar>
		</view>
		<swiper 
		:duration="500" 
		:current="thisindex"  
		:data-index='thisindex' 
		@change="toggle"
		circular v-if="scrollChange == 'true'">
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第一个的内容 -->
				First
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第二个的内容 -->
				Two
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Three
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Four
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Five
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Six
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第一个的内容 -->
				Seven
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第二个的内容 -->
				Eight
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Nine
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Ten
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Eleven
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Twelve
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第一个的内容 -->
				Thirteen
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第二个的内容 -->
				Fourteen
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Fifteen
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Sixteen
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Seventeen
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Eightteen
			</swiper-item>
		</swiper>
		<swiper
		:duration="500" 
		:current="thisindex"  
		:data-index='thisindex' 
		@change="toggle"
		circular v-else-if="scrollChange == 'false'">
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第一个的内容 -->
				First
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第二个的内容 -->
				Two
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第三个的内容 -->
				Three
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第si个的内容 -->
				Four
			</swiper-item>
			<swiper-item class="swiper-item">
				<!-- 按顺序对应第wu个的内容 -->
				Five
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	import navBar from '@/pages/navBar/navBar.vue'
	
	
	export default {
		components:{
			navBar
		},
		data() {
			return {
				target:0,
				thisindex:0,
				
				// false:固定數量的navbar(4 - 6個)；true:可以滑動的navbar
				scrollChange:'false'   //類型為String；Boolean不可用
			}
		},
		methods: {
			// 滑動切换触发的事件
			toggle(e){
				let index = e.detail.current
				this.target = index
			},
			//点击nav控制下面的展示
			setIndex(e){
				this.thisindex = e
			},
		},
		watch:{
			target(val){
				this.setIndex(val)
			}
		}
	}
</script>

<style>
	.nuter{
		width: 100%;
		height: 80rpx;
		line-height: 80rpx;
		display: flex;
		justify-content: space-around;
		font-size: 35rpx;
	}
	.nuter view{
		flex: 1;
		font-size: 30rpx;
		text-align: center;
		transition: all 0.5s ease .1s;
		background-color: #f0f0f0;
	}
	.active{
		box-sizing: border-box;
		color: #007AFF;
		border-bottom: 5rpx solid #00aaff;
		background-color: #f3ffff;
		border-radius: 10rpx;
		box-shadow: 3px 3px 5px #888888;
	}
	swiper{
		height: 80vh;
		width: 100%;
		overflow: hidden;
		text-align: center;
		line-height: 300rpx;
		/* background-color: red; */
	}
	.swiper-item{
		overflow-y: scroll;
		width: 99.5%;
		height: 99%;
		/* background-color: white; */
		/* height: 99%; */
		box-sizing: border-box;
		padding: 1rpx;
	}
</style>
