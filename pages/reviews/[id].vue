<template>
    <div class="container">
        <h2 class="py-5">{{ data.data.attributes.title }}</h2>
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