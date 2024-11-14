<template>
    <view>
        <text selectable>{{ title }}</text>
    </view>

    <view>------</view>

    <scroll-view scroll-y class="scrollView">
        <view v-for="i in 100" :key="i">元素 {{ i }}</view>
    </scroll-view>

    <view>------</view>

    <swiper indicator-dots indicator-color="rgba(255,255,255, 0.5)" indicator-active-color="#fff" circular autoplay>
        <swiper-item v-for="i in 4" :key="i">元素 {{ i }}</swiper-item>
    </swiper>

    <view>------</view>

    <image src="@/static/logo.png"></image>
    <image
        src="../../static/logo.png"
        mode="scaleToFill"
    />

    <view>------</view>

    <button size="mini" style="background-color: blue;" plain @click="goto('/pages/about/about')">关于</button>

    <swiper indicator-dots autoplay circular>
        <swiper-item>hello</swiper-item>
        <swiper-item>hello</swiper-item>
        <swiper-item>hello</swiper-item>
        <swiper-item>hello</swiper-item>
        <swiper-item>hello</swiper-item>
    </swiper>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const title = ref('Hello')
const goto = (url: string) => {
    uni.navigateTo({
        url: url
    })
}
</script>

<style scoped lang="scss">
.scrollView {
    width: 80%;
    height: 100px;
    margin-left: auto;
    margin-right: auto;
    border: 1px solid #ccc;
}

swiper {
    box-sizing: border-box;
    width: 100vw;
    height: 200px;
    border: 1px solid green;

    swiper-item {
        width: 100%;
        height: 100%;
        background-color: pink;
        text-align: center;
    }

    swiper-item:nth-child(2n) {
        background-color: orange;
    }
}
</style>
