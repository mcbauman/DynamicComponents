<script setup>
    const props=defineProps(["value"])
</script>

<template>
    <span>{{ value.key }}</span>
    <select v-model="value.value">
        <option v-for="choise in value.choices" :value="choise">{{choise}}</option>
    </select>
    <input :type="value.type" v-model="value.value">
</template>