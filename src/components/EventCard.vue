<script setup>
defineProps({
  event: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <Router-link class="eventLink" :to="{name: 'event-details', params: { id: event.id }}">
    <div class="eventCard">
      <!-- Display Event Data -->
      <h2>{{ event.title }}</h2>
      <span>@{{ event.time }} on {{ event.date }}</span>
    </div>
  </Router-link>
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

  .eventLink {
    color: #2c3e50;
    text-decoration: none;
  }
</style>
