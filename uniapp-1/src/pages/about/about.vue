<template>
    <view>
        <text selectable>{{ title }}</text>
    </view>
</template>

<script setup lang="ts">
import { ref } from 'vue'
const title = ref('About')
</script>

<style scoped lang="scss"></style>
