<template>
  <div class="container">
    <ReviewList :reviews="data" />
  </div>
</template>

<script setup>
  import { API_URL } from '@/helpers'

  const { data } = await useFetch(API_URL)
</script>

<style scoped>
</style>