<template>
  <view class="goods-item">
    <!-- 商品左侧图片区域 -->
    <view class="goods-item-left">
      <image :src="goods.goods_small_logo || defaultPic" class="goods-pic"></image>
    </view> <!-- 商品右侧信息区域 -->
    <view class="goods-item-right">
      <!-- 商品标题 -->
      <view class="goods-name">{{goods.goods_name}}</view>
      <view class="goods-info-box">
        <!-- 商品价格 -->
        <view class="goods-price">￥{{goods.goods_price |  tofixed}}</view>
      </view>
    </view>
  </view>
</template>

<script>
  export default {
    // 定义 props 属性，用来接收外界传递到当前组件的数据
    props: {
      //商品的信息对象
      goods: {
        type: Object,
        defaul: {},
      },
    },
    name: "my-goods",
    data() {
      return {
        defaultPic: 'https://cdn.cnbj1.fds.api.mi-img.com/mi-mall/96f0d43f0ffc3282349ef1c2bd249339.jpg?w=800&h=532'
      };
    },

      filters: {
        // 把数字处理为带两位小数点的数字 
        tofixed(num) {
          return Number(num).toFixed(2)
      }
    }
  }
</script>

<style lang="scss">
  .goods-item {
    display: flex;
    padding: 20rpx 10rpx;
    border-bottom: 2rpx solid #f0f0f0;

    .goods-item-left {
      margin-right: 10rpx;

      .goods-pic {
        width: 200rpx;
        height: 200rpx;
        display: block;
      }
    }

    .goods-item-right {
      display: flex;
      flex-direction: column;
      justify-content: space-between;

      .goods-name {
        font-size: 26rpx;
      }

      .goods-price {
        font-size: 32rpx;
        color: #c00000;
      }
    }
  }
</style>
