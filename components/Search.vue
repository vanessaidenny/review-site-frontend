<template>
    <div>
      <form @submit.prevent class="form-inline pb-3">
        <input v-model="searchInput" @input="handleSearch" class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search" />
      </form>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const searchInput = ref('');
  
  const handleSearch = (event) => {
    searchInput.value = event.target.value.trim(); 
  
    // Emit the searchInput value to the parent component
    $emit('search', searchInput.value);
  };
  </script>
  
  <style scoped>
  </style>
  