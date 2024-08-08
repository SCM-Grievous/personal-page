<script setup>
import { ref } from 'vue'

var index = 0
const projects = ref([
    {
        name: 'Project 1',
        subtitle: 'Berry College',
        year: 2024,
        img: '/src/assets/placeholder.jpg',
        desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
    },
    {
        name: 'Project 2',
        subtitle: 'Personal',
        year: 2024,
        img: '/src/assets/placeholder.jpg',
        desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
    },
    {
        name: 'Project 3',
        subtitle: 'Personal',
        year: 2023,
        img: '/src/assets/placeholder.jpg',
        desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
    }
])
</script>

<template>
    <div v-for="project in projects" class="container-lg mb-3">
        <div class="row align-items-center">
            <div v-if="index % 2 !== 0" class="col-lg-6">
                <h3>{{ project.name }}</h3>
                <small>{{ project.subtitle }} &bull; {{ project.year }}</small>
                <p>{{ project.desc }}</p>
            </div>
            <div class="col-lg-6">
                <img :src="project.img">
            </div>
            <div v-if="index % 2 === 0" class="col-lg-6">
                <h3>{{ project.name }}</h3>
                <small>{{ project.subtitle }} &bull; {{ project.year }}</small>
                <p>{{ project.desc }}</p>
            </div>
        </div>
        <p style="scale: 0;">{{ index++ }}</p>
    </div>
</template>