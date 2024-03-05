<script setup>
import {onBeforeUnmount, onMounted, ref} from 'vue';
const sheet_id = import.meta.env.VITE_GOOGLE_SHEET_ID;
const api_token = import.meta.env.VITE_GOOGLE_API_KEY;

// import { RouterLink, RouterView } from 'vue-router'
import BaseHeader from '@/components/BaseHeader.vue';
import CardText from '@/components/CardText.vue';
import BaseFooter from '@/components/BaseFooter.vue';
// diese Daten kommen später von der API

let fullData = ref([]);

let emptyData = ref(false);

async function fetchData() {
  const res = await fetch(`https://sheets.googleapis.com/v4/spreadsheets/${sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${api_token}`);
  const data = await res.json();
  fullData.value = data.valueRanges[0].values;
  emptyData.value = data.valueRanges[0].values.length; 
}

const timeInterval = ref("");

function calculateRemainingTime(event) {
  const currentTime = new Date();
  const [day, month, year] = event[1].split('.');

// Erstellen eines Date-Objekts
  const eventTime = new Date(`${year}-${month}-${day}`);

  const timeDifference = eventTime - currentTime;

  const time = new Date(timeDifference);
  const days = Math.ceil(timeDifference / (1000 * 60 * 60 * 24));
  console.log(eventTime)
  console.log(currentTime)

  console.log(time.getUTCDate())

  console.log(timeDifference);

  return days;

}

fetchData();
onMounted(() => {
  timeInterval.value = setInterval(() => {
    fetchData();
  }, 1000 * 60 * 30); // wait 30mins for next update (1000 * 60 * 30)
});
onBeforeUnmount(() => {
  clearInterval(timeInterval.value); // clear the interval when the component is destroyed
});

</script>

<template>
  <!--Header main etc normales html-->
  <header>
    <BaseHeader title="Family Metafuni /Strzyzowski Termine"/>
  </header>

<main>
  <div v-if="fullData.length !==0">
  <CardText v-for="(event,index) in fullData"
    :key=index
    :cardTitle="event[2]"
    :date="event[1]"
    :time="event[0]"
    :text="event[3]"
    :remainingTime="calculateRemainingTime(event)">
  </CardText>
</div>

<div v-else>
    <img class="full-screen-image" src="@/assets/bilder/the-enigmatic-power-of-the-black-aesthetic-u0xe7u4fajxvp3ys.webp" alt="empty">
  </div>
</main>


  <footer>
    <BaseFooter/>
  </footer>
</template>

<style scoped>
.full-screen-image {
  /* width: 100vw;
  height: 100vh; */
  object-fit: cover; /* optional: Behält das Seitenverhältnis bei, deckt aber den gesamten Bereich ab */
}
</style>
