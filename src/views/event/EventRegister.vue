<script setup>
import { useRouter } from 'vue-router'

defineProps(['event'])
const router = useRouter()

const register = () => {
  // pretend registration API call is successful
  router.push({
    name: 'EventDetails'
  })
}
</script>

<template>
  <p>Register for the event here.</p>
  <button @click="register">Register Me!</button>
</template>
