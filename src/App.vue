<script setup>
import {onBeforeMount, onMounted, ref} from 'vue';
const sheet_id = import.meta.env.VITE_GOOGLE_SHEET_ID;
const api_token = import.meta.env.VITE_GOOGLE_API_KEY;

// import { RouterLink, RouterView } from 'vue-router'
import BaseHeader from '@/components/BaseHeader.vue';
import CardText from '@/components/CardText.vue';
import BaseFooter from '@/components/BaseFooter.vue';
// diese Daten kommen später von der API

let fullData;


async function fetchData() {
  const res = await fetch(`https://sheets.googleapis.com/v4/spreadsheets/${sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${api_token}`);
  const data = await res.json();
  fullData = data.valueRanges[0].values;
}

// let fullData = [
//   ['13:30', '11.03.2024', 'WS Persönliche Präsentation', 'Badenerstr. 437', ' default'],
//   ['13:30', '11.03.2024', 'WS Persönliche Präsentation', 'Badenerstr. 437', ' default']
// ];







fetchData();


</script>

<template>
  <!--Header main etc normales html-->
  <header>
    <BaseHeader title="Welcome to Opportunity"/>
  </header>


  <CardText v-for="(event,index) in fullData"
    :key=index
    :cardTitle="event[2]"
    :date="event[1]"
    :time="event[0]"
    :text="event[3]">
  </CardText>



  <footer>
    <BaseFooter/>
  </footer>
</template>

<style scoped>

</style>
