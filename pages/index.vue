<template>
  <div class="container">
    <SearchBar :handleSearch="handleSearch" />
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4">
      <RouterLink v-for="review in displayReviews" :key="review.id" :to="'/reviews/' + review.id" class="col text-decoration-none">
        <div class="card border-0 bg-light h-100 text-center">
          <img
            class="card-img-top align-self-center m-2 shadow-lg"
            :src="review.attributes.image.data.attributes.formats.small.url"
            :alt="review.attributes.title + ' book cover image'"
          />
          <div class="card-body">
            <h5 class="card-title">{{ review.attributes.title }}</h5>
            <i>by {{ review.attributes.author }}</i>
          </div>
          <ul class="list-group list-group-flush border d-flex text-center">
            <li class="list-group-item d-flex flex-row gap-4">
              <small>Rating: {{ review.attributes.rating }}</small>
              <NuxtRating :read-only="true" :ratingValue="review.attributes.rating" :rating-size="'20px'" />
            </li>
          </ul>
        </div>
      </RouterLink>
    </div>
    <div v-if="!displayReviews.length" class="text-center pt-5">
      <p class="mb-0">No reviews found.</p>
    </div>
  </div>
</template>

<script setup>
import { API_URL } from '@/helpers';

const searchValue = ref('');
const { data } = useFetch(API_URL);

// Define reviews data
const reviewsData = computed(() => data.value ? data.value.data : []);

// Display reviews based on search value
const displayReviews = computed(() => {
  const searchTerm = searchValue.value.trim().toLowerCase();
  if (!reviewsData.value || reviewsData.value.length === 0) {
    return [];
  } else if (searchTerm === '') {
    return reviewsData.value;
  } else {
    return reviewsData.value.filter(review => {
      const title = review.attributes.title.toLowerCase();
      return title.includes(searchTerm);
    });
  }
});

// Handle search input
const handleSearch = (value) => {
  searchValue.value = value.trim();
};
</script>

<style scoped>
.card-img-top {
  height: 25rem;
  max-width: min-content;
}

.card:hover {
  background-color: #e5e6ee !important;
}
</style>