<template>
    <div class="container d-md-flex d-flex flex-column flex-md-row flex-lg-row gap-4 gap-lg-5 bg-light rounded p-4">
        <div class="text-center">
            <img class="shadow-lg"
                :src="data.data.attributes.image.data.attributes.formats.small.url"
                :alt="data.data.attributes.title + ' book cover image'"
            />
        </div>
        <div class="d-flex flex-column text-center text-md-start justify-content-start">
            <div class="book-info mb-4">
                <div>
                    <h2 class="fw-semibold display-6">{{ data.data.attributes.title }}</h2>
                    <i>Written by {{ data.data.attributes.author }}</i>
                </div>
                <div class="container d-flex flex-row justify-content-evenly my-4 py-2 border rounded bg-white">
                    <p class="my-0 fw-light">Published: {{ data.data.attributes.year }}</p>
                    <p class="my-0 fw-light">Genre: {{ data.data.attributes.genre }}</p>
                    <p class="my-0 fw-light">Pages: {{ data.data.attributes.pages }}</p>
                </div>
            </div>
            <div class="review-info">
                <h3 class="fw-semibold">Review</h3>
                <div class="d-flex flex-row gap-2 mt-3 mb-2">
                    <p class="my-0">Rating: {{ data.data.attributes.rating }}</p>
                    <NuxtRating :read-only="true" :ratingValue="data.data.attributes.rating" :rating-size="'1.5rem'" />
                </div>
                <p>{{ data.data.attributes.content }}</p>
            </div>
        </div>
    </div>
</template>

<script setup>
    import { BASE_URL, POPULATE_URL } from '@/helpers'

    const route = useRoute()
    const id = route.params.id    

    const { data } = await useFetch(BASE_URL + id + POPULATE_URL)

</script>

<style scoped>
</style>