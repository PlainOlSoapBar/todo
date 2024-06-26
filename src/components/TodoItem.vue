<script setup>
import { defineProps } from 'vue'

const props = defineProps({
    todo: {
        type: Object,
        required: true,
    }
})
</script>

<template>
    <div>
        TodoItem
    </div>
</template>


<style lang="scss" scoped>

</style>