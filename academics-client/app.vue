<template>
  <div v-if="error">
    Error: {{ error.message }}
  </div>
  <div v-else>
    <h2>Students</h2>
    <div>{{ students }}</div>
    <button @click.prevent="refresh">Refresh Data</button>
  </div>
</template>

<script setup>
const { data: students, error, refresh }
    = await useFetch('http://localhost:8080/academics/api/students/all')
</script>
