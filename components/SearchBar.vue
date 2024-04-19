<template>
  <div class="d-flex justify-content-center">
    <form class="form-inline mb-3 col-lg-4">
      <label class="d-flex flex-row align-items-center gap-2">
        Search:
        <input name="searchInput" class="form-control mr-sm-2" type="search" placeholder="Type a Title" aria-label="Search" @input="onInputValueSearch" />
      </label>
    </form>
  </div>
</template>

<script setup>
const { handleSearch } = defineProps(['handleSearch'])

const onInputValueSearch = (event) => {
  handleSearch(event.target.value)
}
</script>

<style scoped>
</style>
