<template>
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4 py-4">
        <div v-for="review in reviews.data" :key="review.id" class="col">
            <RouterLink :to="'/reviews/' + review.id" class="card bg-light h-100 text-center">
                <img
                    class="card-img-top align-self-center p-2"
                    :src="review.attributes.image.data.attributes.formats.small.url"
                    :alt="review.attributes.title + ' book cover image'"
                />
                <div class="card-body">
                    <h5 class="card-title">{{ review.attributes.title }}</h5>
                    <p></p>
                </div>
                <ul class="list-group list-group-flush">
                    <li class="list-group-item">Rating: {{ review.attributes.rating }}</li>
                </ul>
            </RouterLink>
        </div>
    </div>
</template>

<script setup>
    defineProps({
        reviews: Object,
    })
</script>

<style scoped>
    .card-img-top {
        height: 25rem;
        max-width: min-content;
    }

    .card:hover {
        background-color: rgb(209, 214, 228) !important;
    }
</style>
