<template>
    <div class="header-container bg-gradient shadow-sm">
        <header class="container py-5">
            <div class="d-flex flex-column align-items-center gap-2">
                <h1 class="display-4">Book Review Site</h1>
                <nav>
                    <NuxtLink to="/" class="fs-5 text-decoration-none fw-semibold">All Reviews</NuxtLink>
                </nav>
            </div>
        </header>
    </div>

    <!-- Output the page content -->
    <div class=" py-5">
        <slot />
    </div>
</template>
    
  
<script setup>
</script>

<style scoped>
    .header-container {
        background-color: #dadbf4;
    }

    nav a {
        color: #191c6e !important;
    }
    nav a:hover {
        color: #030421 !important;
    }
    .router-link-active {
        text-decoration: underline !important;
        font-weight: bold !important;
    }
    
    * {
        font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif !important;
    }
</style>