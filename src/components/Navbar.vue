<script setup>
import DarkModeSwitcher from './DarkModeSwitcher.vue'
</script>

<template>
    <nav class="navbar navbar-expand-sm bg-light-subtle sticky-top">
        <div class="container-lg">
            <a class="navbar-brand" href="#">Nathan Moore</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse justify-content-end" id="navbarSupportedContent">
                <ul class="navbar-nav align-items-center">
                    <li class="nav-item px-2"><a class="nav-link px-2" href="#">Resum&#233;</a></li>
                    <li class="nav-item"><DarkModeSwitcher /></li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<style scoped>
.navbar {
    box-shadow: 0;
    transition: all 0.5s;
}

.navbar:hover {
    box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15);
}
</style>