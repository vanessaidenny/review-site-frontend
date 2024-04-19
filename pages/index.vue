<template>
    <div class="container">
      <ReviewList :reviews="filteredReviews" />
    </div>
  </template>
  
<script setup>
    import { API_URL } from '@/helpers'

    const { data: reviewsData } = await useFetch(API_URL)
    const searchQuery = ref('');

    const handleSearch = (query) => {
      searchQuery.value = query;
    };

    const filteredReviews = computed(() => {
      if (!reviewsData.value || !reviewsData.value.data) return [];
      
      const searchTerm = searchQuery.value.trim().toLowerCase();
      return reviewsData.value.data.filter((review) =>
        review.attributes.title.toLowerCase().includes(searchTerm)
      );
    });
</script>

<style scoped>
</style>