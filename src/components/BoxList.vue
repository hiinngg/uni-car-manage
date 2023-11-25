<template>
  <view class="boxlist__container">
    <view class="boxlist__main">
  
      <uni-swipe-action class="">
        <view class="boxlist__item__wrapper" v-for="(data,index) in props.dataList" :key="index">
      <uni-swipe-action-item  >
        <view class="boxlist__item ">
          <view class="boxlist__item__left">
            <view class="boxlist__item__icon">
              <img
                v-if="data.redcar"
                class="boxlist__item__icon__redcar"
                :class="{'boxlist__item__icon__redcar--space': data.bluecar}"
                src="../static/index/redcar1.png"
                alt=""
              />
              <img
                v-if="data.bluecar"
                class="boxlist__item__icon__bluecar"
                src="../static/index/bluecar1.png"
                alt=""
              />
            </view>
            <view class="boxlist__item__info" v-if="data.username">
              <uni-icons type="contact" size="30"></uni-icons>
              <view class="boxlist__item__info__text">{{data.username}}</view>
            </view>
          </view>
          <view class="boxlist__item__status--active" v-if="data.ready">准备就绪</view>
          <view class="boxlist__item__status--disabled" v-if="data.disabled">维修中</view><!-- <view class="boxlist__item__status--disabled">维修中</view> -->
        </view>
        <template #right>
          <view class="boxlist__item__right"   v-if="data.allowDel">
            <view class="boxlist__item__del">退场</view>
          </view>
        </template>
      </uni-swipe-action-item>
      </view>
      </uni-swipe-action>
      </view>
    </view>
</template>

<script setup >
const props = defineProps({
        dataList:{
            default:()=>[],
            type:Array
        }

})



</script>

<style lang="scss" scoped>
.boxlist {
  &__container {
    background-color: #f5f6f7;
    height: 100%;
    overflow-x: hidden;
    width: 100%;
    box-sizing: border-box;
  }
  &__main {
    height: 100%;
    overflow-x: hidden;
    padding:0 0 30rpx 0;
    width: 100%;
    overflow-y: auto;
    box-sizing: border-box;
  }
  &__item {
    width: 626rpx;
    height: 88rpx;
    background-color: #ffffff;
    margin: 0 auto;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 30rpx;

    &__status--active {
      font-size: 28rpx;
      font-family: PingFang SC;
      font-weight: bold;
      color: #3ac081;
    }
    &__status--disabled {
        font-size: 28rpx;
        font-family: PingFang SC;
        font-weight: bold;
        color: #FF0000;
    }

    &__left {
      display: flex;
      align-items: center;
    }
    &__info {
      display: flex;
      align-items: center;
      margin-left: 38rpx;

      &__text {
        font-size: 30rpx;
        font-family: PingFang SC;
        font-weight: 400;
        color: #333232;

        margin-left: 15rpx;
      }
    }

    &__icon {
      // display: flex;
      // align-items: end;

      &__redcar {
        width: 75rpx;
        height: 48rpx;
      
      &--space{
        margin-right: 22rpx;
      }
      }

    

      &__bluecar {
        width: 76rpx;
        height: 60rpx;

      }
    }

    &__del {
      margin-left: 32rpx;
      width: 120rpx;
      height: 56rpx;
      border: 1rpx solid #ff0000;
      border-radius: 28rpx;
      font-size: 28rpx;
      font-family: PingFang SC;
      font-weight: bold;
      color: #ff0000;
      line-height: 56rpx;
      text-align: center;
      margin-right: 30rpx;
    }

    &__right {
      display: flex;
      align-items: center;
      height: 100%;
    }
    &__wrapper {
      margin-top: 30rpx;
      height: 88rpx;
    }
  }
}
</style>
