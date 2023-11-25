<template>
  <navbar title="车场管理"></navbar>
  <mainView></mainView>
  <view class="footer__wrapper">
    <!-- 底部导航 -->
    <view class="footer__item">
      <image class="footer__item__icon" src="../static/index/manage.png" alt="" />
      <view class="footer__item__text footer__item__text--active"
        >车场管理</view
      >
    </view>
    <view class="footer__item">
      <image class="footer__item__icon" src="../static//index/user.png" alt="" />
      <view class="footer__item__text">我的</view>
    </view>
  </view>
</template>

<script setup lang="ts">
import navbar from "@/components/navbar.vue";
import mainView from '../mainView.vue'
</script>
<style scoped lang="scss">


  .footer {
    &__wrapper {
      /* 底部导航栏的样式 */
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      background-color: #ffffff;
      text-align: center;
      box-sizing: border-box;
      height: 98rpx;
      display: flex;
      align-items: center;
      justify-content: space-around;
    }

    &__item {
      margin-top: 12rpx;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100%;

      &__icon {
        width: 40rpx;
        height: 42rpx;
      }
      &__text {
        margin-top: 9rpx;
        font-size: 24rpx;
        font-family: Microsoft YaHei;
        font-weight: 400;
        color: #b3b3b3;

        &--active {
          color: #0076ff;
          background: linear-gradient(0deg, #6fbeff 0%, #a1ffd1 100%);
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
        }
      }
    }
  }

</style>
