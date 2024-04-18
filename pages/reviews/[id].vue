<template>
    {{ data }}
</template>

<script setup>
    import { BASE_URL } from '@/helpers'

    const route = useRoute()
    const id = route.params.id

    const { data } = await useFetch(BASE_URL + id)
</script>

<style scoped>
</style>