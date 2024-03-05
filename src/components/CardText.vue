<script setup>
defineProps(['cardTitle','time', 'text', 'date','remainingTime']);


</script>

<template>
    <div class="card">
      <div class="inner-card">
            <div class="card-date">
                <p>{{ date }}</p>
                <p>noch{{ remainingTime }} Tag(e)</p>
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
    padding: 2px;
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
    width: 100%;
    max-width: 950px;
    height: fit-content;
    top: 276px;
    left: 60px;
}

.inner-card{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    width: 100%;
    max-width: 950px;
    height: fit-content;
    top: 37px;
    left: 40px;
    margin: 40px;
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