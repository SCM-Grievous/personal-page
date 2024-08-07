<script setup>
import { ref } from 'vue';

// Initial dark mode setting based on browser preferences
const darkMode = ref(window.matchMedia('(prefers-color-scheme: dark)').matches)
document.documentElement.setAttribute('data-bs-theme', darkMode.value ? 'dark' : 'light')

function clickEventHandler(e) {
    darkMode.value = !darkMode.value
    document.documentElement.setAttribute('data-bs-theme', darkMode.value ? 'dark' : 'light')
}
</script>

<template>
    <div class="form-check form-switch">
        <input @click="clickEventHandler" class="form-check-input" type="checkbox" :checked="darkMode" role="switch" id="switcher">
        <label class="form-check-label" for="switcher">
            <Transition>
                <i v-if="!darkMode" class="bi bi-sun" alt="Light mode"></i>
                <i v-else class="bi bi-moon" alt="Dark mode"></i>
            </Transition>
        </label>
    </div>
</template>

<style scoped>
.form-check-input {
    border-color: gray;
    color: blueviolet
}

.form-check-input:checked {
    background-color: rgb(138, 43, 226);
    border-color: gray;
}

.form-check-input:focus {
    box-shadow: 0 0 0 0.25rem rgba(138, 43, 226, 0.25);
    color: gray;
    border-color: #808080;
}

.v-enter-active {
    transition: all 0.5s;
}

.v-enter-from {
    opacity: 0;
}
</style>