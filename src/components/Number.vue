<script setup>
    const props=defineProps(["value"])
</script>

<template>
    <span>{{ value.key }}</span>
    <input :type="value.type" v-model="value.value">
</template>