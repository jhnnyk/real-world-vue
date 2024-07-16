<script setup>
import axios from 'axios'
import EventCard from '@/components/EventCard.vue'
import { ref, onMounted } from 'vue'

const events = ref(null)

onMounted(() => {
  axios
    .get('https://my-json-server.typicode.com/Code-Pop/Real-World_Vue-3/events')
    .then((response) => {
      events.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
</script>

<template>
  <h1>Events for Good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
