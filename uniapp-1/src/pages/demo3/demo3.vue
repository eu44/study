<template>
    <view class="out">
        <view class="item" v-for="(item, index) in goods" :key="item.id">
            <checkbox />
            <text class="title">{{ item.name }}</text>
            <text class="del" @click="rm(index)">删除</text>
        </view>

    </view>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const goods = ref([{
    id: 111,
    name: '小米',
}, {
    id: 222,
    name: '华为',
}, {
    id: 333,
    name: '苹果',
}, {
    id: 444,
    name: 'OPPO',
}, {
    id: 555,
    name: 'vivo',
}, {
    id: 666,
    name: '魅族',
}])

const rm = (index: number) => {
    goods.value.splice(index, 1)
}
</script>

<style lang="scss" scoped>
.out {
    padding: 10px;

    .item {
        padding: 10px 0;

        .del {
            color: red;
            margin-left: 20px;
        }
    }
}
</style>