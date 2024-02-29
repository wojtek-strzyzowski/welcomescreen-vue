<script setup>
defineProps(['cardTitle','time', 'text', 'date']);


</script>

<template>
    <div class="card">
        <div class="card-header">
            <h2>{{ cardTitle }}</h2>
        </div>
        <div class="card-time">
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

.card-time {
    color: red;
}

.card-body {
    color: gold;
}

</style>