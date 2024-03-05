<script setup>
defineProps(['cardTitle','time', 'text', 'date']);


</script>

<template>
    <div class="card">
      <div class="inner-card">
            <div class="card-date">
                <p>{{ date }}</p>
            </div>
            
            <div class="card-time">
                <p>{{ time }}</p>
            </div>

            <div class="card-header">
                <h2>{{ cardTitle }}</h2>
            </div>

            <div class="card-body">
                <p> {{ text }}</p>
            </div>
        </div> 
    </div>

</template>

<style scoped>

div, p, h2 {
    margin: 0;
    font-size: 26px;
}
.card{
    display: flex;
    flex-direction: column;
    background-color: blue;
    font-size: 26px;
    margin: 20px;
    size: 28px;
    top: 37px;
    left: 40px;
    width: 919px;
    height: 182px;
    top: 276px;
    left: 60px;
}

.inner-card{
    width: 755px;
    height: 108px;
    top: 37px;
    left: 40px;
    padding: 40px;
}

.card-date {
    font-size: 30px;
    margin: 0;
}
.card-header {
    color: gold;
    font-size: 26px;
    margin: 0;
}

.card-time {
    color: orangered;
    font-weight: bold;
    font-size: 30px;
    margin: 0;
}

.card-body {
    color: gold;
    font-size: 26px;
    margin: 0;
}

.Image {
    width: 100vw;
    height: 100vh;
}

</style>