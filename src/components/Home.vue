<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

const user = ref()
onMounted(async () => {
  const data = await axios.get('/api/user')
  user.value = data.data
})
</script>
<template>
  <div class="max-w-7xl mx-auto">
    <h2>Hello</h2>
    <div v-if="true">
      <h1>{{ user?.name }}</h1>
      <p>{{ user?.email }}</p>
    </div>
    <div v-else>
      <h1>Go and login</h1>
    </div>
  </div>
</template>
