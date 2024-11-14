<template>
    <view class="box" @click="onClick" :style="{ backgroundColor: color }">
        {{ num }}
    </view>
    <switch @change="onChange" />

    <br>
    <button class="button-class" size="mini" :loading="isLoding" hover-class="button-hover">
        按钮
    </button>

</template>

<script lang="ts" setup>
import { ref } from 'vue'

const color = ref('#fff')
const num = ref(0)
const isLoding = ref(false)

const onClick = () => {
    num.value++
    color.value = "#" + String(Math.floor(Math.random() * 16777215).toString(16))
    console.log(color.value)
}

const onChange = (e: any) => {
    isLoding.value = e.detail.value
}
</script>

<style lang="scss" scoped>
.box {
    width: 100px;
    height: 100px;
    background-color: blue;
}

.button-class {
    background-color: #4CAF50;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 16px;
    cursor: pointer;
}
.button-hover {
    background-color: #008CBA;
}
</style>