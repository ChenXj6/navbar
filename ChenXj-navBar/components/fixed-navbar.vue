
<template>
	<view class="content">
		<view class="nuter">
			<view
			v-for="(item, index) in navArr" 
			:key="item.url" 
			class="nav-item"
			:class="target == index?'active':''"
			@click="tabChange(index)"
			:id="'item-' + index"
			>
				<text class="title">{{item.title}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props:{
			navArr: {
				type: Array,
				default () {
					return [
						{
							title: '最新上架',
							url: 'recent'
						}, {
							title: '全部',
							url: 'all'
						}, {
							title: '文学',
							url: 'literature'
						}, {
							title: '小说',
							url: 'novel'
						}, {
							title: '教育',
							url: 'education'
						}
					]
				}
			},
			scrollChangeIndex:{
				type: Number,
				default: 0
			},
		},
		data() {
			return {
				target:0,
			}
		},
		methods: {
			tabChange (index) {
				this.$emit('navbarTap',index);
				this.target = index
			},
		},
		watch:{
			scrollChangeIndex(val){
				this.tabChange(val)
			},
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
