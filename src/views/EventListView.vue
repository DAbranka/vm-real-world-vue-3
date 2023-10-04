<script setup>
import EventCard from '@/components/EventCard.vue';
import { ref } from 'vue';

let id = 0

const events = ref([
  {
    id: id++,
    category: 'animal welfare',
    title: 'Cat Adoption Day',
    description: 'Find your new feline friend at this event.',
    location: 'Meow Town',
    date: 'January 28th, 2022',
    time: '12:00',
    petsAllowed: true,
    organizer:  'Kat Laydee'
  },
  {
    id: id++,
    category: 'food',
    title: 'Community Gardening',
    description: 'Join us as we tend to the community edible plants.',
    location: 'Flora City',
    date: 'March 14th, 2022',
    time: '10:00',
    petsAllowed: true,
    organizer:  'Fern Pollin'
  },
  {
    id: id++,
    category: 'sustainability',
    title: 'Beach Cleanup',
    description: 'Help pick up trash along the shore.',
    location: 'Playa Del Carmen',
    date: 'July 22nd, 2022',
    time: '11:00',
    petsAllowed: false,
    organizer:  'Carey Wales'
  },
])
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
