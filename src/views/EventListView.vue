<script setup>
import EventCard from '@/components/EventCard.vue';
import { ref, onMounted } from 'vue';
import EventService from '@/services/EventService';

const events = ref(null)

// * Fetching data with Axios
onMounted(() => {
  EventService.getEvents()
  .then((response) => {
    events.value = response.data
    console.log('event:', response.data)
  })
  .catch((error) => {
    console.log(error)
  })
})
console.log(events.value)
</script>

<template>
  <h1>Events For Good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event"/>
  </div>
</template>

<style scoped>
  .events {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
