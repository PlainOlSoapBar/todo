<script setup></script>

<template>
    <button>
        <slot>Create</slot>
    </button>
</template>


<style lang="scss" scoped>
    button {
        padding: 8px 16px;
        border: none;
        transition: 0.3s ease;
    }

    button:hover {
        background-color: rgb(200, 200, 200);
        transition: background-color 0.3s ease;
    }

</style>