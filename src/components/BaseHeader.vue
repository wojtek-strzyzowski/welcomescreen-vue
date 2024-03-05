<script setup>

defineProps(['title']);

import { ref, onMounted } from 'vue';

let currentDate = ref('');

onMounted(() => {
  updateCurrentDate();
});

const updateCurrentDate = () => {
  const now = new Date();
  const options = { weekday: 'short', year: 'numeric', day: 'numeric', month: 'numeric' };
  currentDate.value = now.toLocaleDateString('en-US', options);
};

</script>

<template>
<header>
    <h1>{{title}}</h1>
    <p>{{ currentDate }}</p>
</header>
</template>

<style scoped>


</style>


