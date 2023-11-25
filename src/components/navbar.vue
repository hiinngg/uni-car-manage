<template>
  <view class="navbar__container">
        <view class="status_bar">
            <!-- 这里是状态栏 -->
        </view>
        <view class="navbar__text">{{props.title}}</view>
    </view>
</template>

<script setup lang="ts">
const props = defineProps({
    title:{
        type:String
    }
})

</script>

<style lang="scss" scoped>
    .status_bar {
        height: var(--status-bar-height);
        width: 100%;
    }

    .navbar{
        &__container{
            height: 128rpx;
            background-image: url('../static/navbar.png');
        }

        &__text{
            text-align: center;
            font-size: 36rpx;
            font-family: PingFang SC;
            font-weight: 400;
            color: #333333;
        }
    }    


</style>
