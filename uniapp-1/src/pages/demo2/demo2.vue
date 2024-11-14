<template>
    <button size="mini" plain @click="show =!show">按钮</button>
    <view>
        <view v-if="show">京东</view>
        <view v-else>淘宝</view>
    </view>

    <view v-if="day === 0">周1</view>
    <view v-else-if="day === 1">周2</view>
    <view v-else-if="day === 2">周3</view>
    <view v-else-if="day === 3">周4</view>
    <view v-else-if="day === 4">周5</view>
    <view v-else-if="day === 5">周6</view>
    <view v-else-if="day === 6">周天</view>
    <view v-else>格式错误</view>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const show = ref(true)

const day = ref(3)

setInterval(() => {
    day.value = ++day.value % 7
}, 1000);
</script>

<style lang="scss" scoped></style>