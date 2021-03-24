<template>
	<view class="content">
		<view class="uni-form-item uni-column">
		          <picker @change="examinationType" :range="arr" :range-key="'gender'">
					  <label>性别筛选：</label><br />
					   <label>请选择：</label><br />
		              <label class="">{{ arrnameArr }}</label><br />
					   <label >筛选结果：男{{ objs }}</label><br />
					   <label >筛选结果：女{{ obj }}</label><br />
					  
		          </picker>

	</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				arr:[
					{gender:'男'},
					{gender:'女'},
					],
				arrnameArr:[
					{name:'joker',gender:'男'},
					{name:'lucy',gender:'女'},
					{name:'john',gender:'男'},
					{name:'rose',gender:'女'},
				],
				objs:[],
				obj:[]
			}
		},
		onLoad() {
		},
		methods: {
onPullDownRefresh() {
        setTimeout(()=> {
            uni.stopPullDownRefresh();
        }, 1000);
		this.objs =[]
		this.obj = []
    },
	 examinationType(e) {
		let array = this.arrnameArr
		 for (let i=0;i<array.length;i++) {
			 if(array[i].gender==='男'){
				 this.objs.push(array[i].name)
			 }
			 else {
				 this.obj.push(array[i].name)
			 }
		 }
	    }
		},
		
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
