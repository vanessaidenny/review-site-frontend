<template>
  <!-- Navigation Bar using Bootstrap -->
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <!-- Toggler button on the right -->
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      
      <!-- Navbar content that collapses -->
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto"> <!-- ms-auto will keep the nav to the right -->
          <li class="nav-item">
            <RouterLink :to="'/'" class="nav-link">Home</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink :to="'#'" class="nav-link">Review</RouterLink>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <!-- Main Content Area -->
  <div class="row p-5 pb-4 justify-content-lg-between g-4 bg-light">
    <h1 class="text-center col-lg-6 col-lg-text-left">Book Review Site</h1>
    <Search class="col-lg-4" />
  </div>

  <!-- Nuxt Page Content, where individual pages are rendered -->
  <NuxtPage />
</template>

<script setup>
</script>

<style scoped>
.container-fluid {
  display: flex;
  justify-content: flex-end; /* Aligns toggler to the right */
}
</style>

