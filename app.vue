<template>
  <!-- Main Content Area -->
  <div class="container mt-5">
    <div class="text-center mb-4">
      <h1>Book Review Site</h1>
    </div>
    <div class="d-flex justify-content-between align-items-center">
      <!-- Search Component -->
      <Search class="flex-grow-1 me-3" />
      <!-- Back to Home Button -->
      <NuxtLink to="/" class="btn btn-primary">Back to Home</NuxtLink>
    </div>
  </div>

  <!-- Nuxt Page Content, where individual pages are rendered -->
  <NuxtPage />
</template>

<script setup>
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.btn-primary:hover {
  background-color: green; 
  color: #ffffff; /* Optional: change text color on hover */
}
</style>
