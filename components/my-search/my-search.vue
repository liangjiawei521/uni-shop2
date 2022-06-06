<template>
  <view class="my-search-container" >
    <!-- 使用 view 组件模拟 input 输入框的样式 -->
    <view class="my-search-box" @click="searchBoxHandler">
      <uni-icons type="search" size="17"></uni-icons>
      <text class="placeholder">搜索</text>
    </view>
  </view>
</template>

<script>
  export default {

    data() {
      return {

      }
    },
    methods:{
      searchBoxHandler(){
        this.$emit('click')
      }
    }
  }
</script>

<style lang="scss">
  .my-search-container {
    background-color: #c00000;
    height: 100rpx;
    padding: 0 20rpx;
    display: flex;
    align-items: center;
  }

  .my-search-box {
    height: 72rpx;
    background-color: #ffffff;
    border-radius: 36rpx;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;

    .placeholder {
      font-size: 30rpx;
      margin-left: 10rpx;
    }
  }
</style>
