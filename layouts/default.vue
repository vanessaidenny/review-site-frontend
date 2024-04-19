<template>
    <div>
        <header class="container mt-5">
        <div class="text-center mb-4">
            <h1>Book Review Site</h1>
        </div>
        <div class="d-flex justify-content-between align-items-center">
            <!-- Search Component -->
            <Search class="flex-grow-1 me-3" />
            <!-- Back to Home Button -->
            <nav>
                <NuxtLink to="/" class="btn btn-primary">Back to Home</NuxtLink>
            </nav>
        </div>
        </header>
  
        <!-- Output the page content -->
        <div>
            <slot />
        </div>
    </div>
</template>
    
  
<script setup>
</script>

<style scoped>
</style>