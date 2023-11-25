<template>
  <view class="boxheader__container">
    <view class="boxheader__title">
      <view class="boxheader__title__border"></view>
      <view class="boxheader__title__desc">{{props.title}}</view>
    </view>
    <view class="boxheader__oper">
      <view class="boxheader__oper__status" v-if="props.statusDisplay">
        <view class="boxheader__oper__status__circle"></view>
        <view class="boxheader__oper__status__text">准备中</view>
      </view>

      <view class="boxheader__oper__btn boxheader__oper__btn--active" v-if="props.btnActive">开局</view>
      <view class="boxheader__oper__btn boxheader__oper__btn--disable" v-else>入场</view>
    </view>
  </view>
</template>

<script setup>
const props = defineProps({
  statusDisplay: {
    type: Boolean,
    default: false,
  },
  btnActive: {
    type: Boolean,
    default: false,
  },
  title:{
    type: String,
    default: "",
  }
});
</script>

<style scoped lang="scss">
.boxheader {
  &__container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom:45rpx;
  }

  &__title {
    display: flex;
    align-items: center;

    &__desc {
      font-size: 30rpx;
      font-family: PingFang SC;
      font-weight: bold;
      color: #333333;
      line-height: 38rpx;
    }

    &__border {
      width: 6rpx;
      height: 30rpx;
      background: linear-gradient(0deg, #6fbeff 0%, #a1ffd1 100%);
      border-radius: 3rpx;
      margin-right: 14rpx;
    }
  }

  &__oper {
    display: flex;
    align-items: center;

    &__btn {
      width: 120rpx;
      height: 56rpx;

      border-radius: 28rpx;
      text-align: center;
      line-height: 56rpx;
      font-size: 28rpx;
      font-family: PingFang SC;
      font-weight: bold;
      color: #ffffff;

      &--active {
        background: linear-gradient(90deg, #6fbeff 0%, #a1ffd1 100%);
      }
      &--disable {
        background: #9d9d9d;
      }
    }

    &__status {
      display: flex;
      align-items: center;
      margin-right: 28rpx;
      &__circle {
        width: 16rpx;
        height: 16rpx;
        background: #ffba00;
        border-radius: 50%;
      }

      &__text {
        font-size: 28rpx;
        font-family: PingFang SC;
        font-weight: bold;
        color: #ffba00;
        line-height: 38rpx;
        margin-left: 18rpx;
      }
    }
  }
}
</style>
