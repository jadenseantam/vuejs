<template>
    <div>
        <button @click="add">Counter: {{ count }}</button>
    </div>
</template>

<script setup>
import { ref } from 'vue';

let count = ref(0)

const add = () => {
    count.value++
}
</script>

<style lang="scss" scoped>

</style>