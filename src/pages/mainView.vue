<template>
    <view class="content">
    <!-- main -->
    <view class="content__box content__choose">
      <!-- 下拉选择 -->
      <view>极限xr飞碟车场</view>
      <img class="content__choose__img" src="../static/index/dropdown.png" alt="" />
    </view>

    <view class="content__box content__queuing-area">
      <!-- 排队区 -->
      <BoxHeader title="排队区"></BoxHeader>
      <BoxList :dataList="queuingAreaList" style="flex: 1"></BoxList>
    </view>
    <view class="content__box content__parking-area">
      <!-- 车场内 -->
      <BoxHeader title="车场内" :statusDisplay="true" :btnActive="true"></BoxHeader>
      <BoxList :dataList="parkingAreaList" style="flex: 1"></BoxList>
    </view>
  </view>

</template>


<script>
const queuingAreaList = [
  { redcar: true },
  { bluecar: true },
  { bluecar: true },
  { bluecar: true },
  { bluecar: true, disabled: true },
];
const parkingAreaList = [
  {
    redcar: true,
    bluecar: true,
    username: "萌新蛋仔",
    ready: true,
    allowDel:true
  },
  {
    redcar: true,
    bluecar: true,
    username: "大宝狮子",
    ready: true,
    allowDel:true
  },
  {
    redcar: true,
    bluecar: true,
    username: "散客",
    ready: true,
    allowDel:true
  },
  {
    bluecar: true,
    allowDel:true

  },
];

export default {
    name:'CarManage'
}
</script>
<script setup >
import BoxHeader from "../components/BoxHeader.vue";
import BoxList from "../components/BoxList.vue";
</script>

<style scoped lang="scss">

.content {
    background-color: #f5f6f7;
    height: 100vh;
    overflow-y: auto;
    padding: 128rpx 0;
    box-sizing: border-box;
    width: 100%;

    &__box {
      background-color: #ffffff;
      width: 100%;
      box-sizing: border-box;
    }

    &__queuing-area {
      height: 867rpx;
      padding: 42rpx 30rpx 30rpx 30rpx;
      display: flex;
      flex-direction: column;
    }

    &__choose {
      display: flex;
      align-items: center;
      border-bottom: 1rpx solid #f5f6f7;
      height: 96rpx;
      font-size: 30rpx;
      font-weight: bold !important;
      color: #333333;
      padding: 0 30rpx;

      &__img {
        width: 24rpx;
        height: 14rpx;
        margin-left: 15rpx;
      }
    }

    &__parking-area {
    //   height: 623rpx;
      margin-top: 20rpx;
      padding: 30rpx 30rpx 30rpx 30rpx;
      display: flex;
      flex-direction: column;
    }
  }
</style>