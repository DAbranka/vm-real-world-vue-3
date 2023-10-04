<script setup>
import { ref } from 'vue';
// defineProps({
//   msg: {
//     type: String,
//     required: true
//   }
// })

let id = 0

const event = ref([
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
])
console.log(event.value)
</script>

<template>
  <div class="eventCard">
    <!-- Display Event Data -->
    <h2>{{ event[0].title }}</h2>
    <span>@{{ event[0].time }} on {{ event[0].date }}</span>
  </div>
</template>

<style scoped>
  .eventCard {
    padding: 20px;
    width: 250px;
    cursor: pointer;
    border: 1px solid #39495c;
    margin-bottom: 18px;
  }

  .eventCard:hover {
    transform: scale(1.01);
    box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
  }
</style>
