<template>
	<view class="container">
		<view class="intro">通用模板</view>
		<text class="intro">详见：</text>
    <u-button type="primary">按钮</u-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				href: 'https://uniapp.dcloud.io/component/README?id=uniui'
			}
		},
    created() {
      uni.request({
          url: 'http://apitest.xiniaogongkao.com/appv1/banner', //仅为示例，并非真实接口地址。
          method: 'post',
          data: {
              text: 'uni.request'
          },
          header: {
              'custom-header': 'hello', //自定义请求头信息
              'content-type': 'application/x-www-form-urlencoded'
          },
          success: (res) => {
              console.log(res.data);
              this.text = 'request success';
          }
      });
    },
		methods: {
      
		}
	}
</script>

<style>
	.container {
		padding: 20px;
		font-size: 32rpx;
		line-height: 64rpx;
	}
</style>
