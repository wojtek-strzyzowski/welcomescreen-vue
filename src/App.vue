<script setup>

import { RouterLink, RouterView } from 'vue-router'
import BaseHeader from '@/components/BaseHeader.vue'
import CardText from '@/components/CardText.vue'
import BaseFooter from '@/components/BaseFooter.vue'
// diese Daten kommen später von der API
let events = [
  {id: 1, cardTitle: '', date: '', time: '', text: ''},
  {id: 2, cardTitle: '', date: '', time: '', text: ''},
  {id: 3, cardTitle: '', date: '', time: '', text: ''},
];



</script>

<template>
  <!--Header main etc normales html-->
  <header>
    <BaseHeader title="Welcome to Opportunity"/>
  </header>

  <main>
    <CardText v-for="event in events"
    :key="event.id"
    :cardTitle="event.cardTitle"
    :date="event.date"
    :time="event.time"
    :text="event.text"/>
  </main>

  <footer>
    <BaseFooter/>
  </footer>
  <RouterView />
</template>

<style scoped>

</style>
