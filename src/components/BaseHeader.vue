<script setup>

defineProps(['title']);

</script>

<template>
<header>
    <h1>{{title}}</h1>
</header>
</template>

<style scoped>
h1 {
    font-size: 3rem;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>