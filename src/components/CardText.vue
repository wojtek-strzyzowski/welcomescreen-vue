<script setup>
defineProps(['cardTitle', 'date','time', 'text']);


</script>

<template>
    <div class="card">
        <div class="card-header">
            <h2>{{ cardTitle }}</h2>
            <p>{{ time }}</p>
        </div>
        <div class="card-body">
            <p> {{ text }}</p>
        </div>
    </div>
</template>

<style scoped>
.card{
    background-color: blue;
}

.card-header {
    color: gold;
}
.card-body {
    color: gold;
}

</style>