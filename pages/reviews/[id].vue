<template>
    <div class="ps-4 pt-3">
        <RouterLink to="/" class="text-decoration-none">
            <button type="button" class="btn btn-dark btn-sm">Back to Home</button>
        </RouterLink>
    </div>    
    <div class="container-fluid d-md-flex p-3">
        <div class="text-center">
            <img class="px-2"
                :src="data.data.attributes.image.data.attributes.formats.small.url"
                :alt="data.data.attributes.title + ' book cover image'"
            />
        </div>        
        <div class="d-flex flex-column text-center text-md-start px-2">
            <h2 class="pt-2">{{ data.data.attributes.title }}</h2>
            <h5 class="pt-2">{{ data.data.attributes.author }}</h5>
            <p>Rating: {{ data.data.attributes.rating }}</p>
            <div class="text-start">
                <p>{{ data.data.attributes.content }}</p>
                <p class="fw-light">Published: {{ data.data.attributes.year }}</p>
                <p class="fw-light">Genre: {{ data.data.attributes.genre }}</p>
                <p class="fw-light">Pages: {{ data.data.attributes.pages }}</p>
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