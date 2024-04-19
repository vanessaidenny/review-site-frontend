<template>
    <Search />
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4 g-4">
        <div v-for="review in reviews" :key="review.id" class="col">
            <RouterLink :to="'/reviews/' + review.id" class="text-decoration-none">
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
                    <ul class="list-group list-group-flush border">
                        <li class="list-group-item">Rating: {{ review.attributes.rating }}</li>
                    </ul>
                </div>
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
        background-color: #e5e6ee !important;
    }
</style>
