<script setup>
import { ref } from 'vue'
import Navbar from './Navbar.vue'
import ProjectList from './ProjectList.vue'
import '../assets/main.css'

const showAboutMe = ref(false)

</script>

<template>
    <Navbar />

    <div class="container-lg pt-4">
        <div class="row align-items-center">
            <div class="col-lg-6">
                <Transition name="fade">
                    <h1 v-if="!showAboutMe" class="fw-bold slide">Hero message</h1>
                    <h1 v-else class="fw-bold slide">About me</h1>
                </Transition>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore
                    et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
                    aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
                    cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
                    culpa qui officia deserunt mollit anim id est laborum.</p>
                <Transition name="slide-fade">
                    <p v-if="showAboutMe">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
                        labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
                        laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
                        voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                        non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                    </p>
                </Transition>
                <div class="container-lg text-center">
                    <button @click="showAboutMe = !showAboutMe" class="btn">
                        <Transition name="button-fade">
                            <span v-if="!showAboutMe" class="pe-2">Read more</span>
                            <span v-else class="pe-2">Read less</span>
                        </Transition>
                        <Transition name="button-fade">
                            <i v-if="!showAboutMe" class="bi bi-chevron-down"></i>
                            <i v-else class="bi bi-chevron-up"></i>
                        </Transition>
                    </button>
                    <p class="mb-2">or <a href="#" class="link-underline link-underline-opacity-0">view my
                            resum&#233;</a></p>
                </div>
            </div>

            <div class="col-lg-6">
                <div id="carousel" class="carousel slide shadow" data-bs-ride="carousel">
                    <div class="carousel-indicators">
                        <button type="button" data-bs-target="#carousel" data-bs-slide-to="0" class="active bg-dark"
                            aria-current="true" aria-label="Slide 1"></button>
                        <button type="button" data-bs-target="#carousel" data-bs-slide-to="1" class="bg-dark"
                            aria-label="Slide 2"></button>
                        <button type="button" data-bs-target="#carousel" data-bs-slide-to="2" class="bg-dark"
                            aria-label="Slide 3"></button>
                    </div>
                    <div class="carousel-inner">
                        <div class="carousel-item active">
                            <img src="../assets/placeholder.jpg" class="d-block w-100" alt="A placeholder image">
                        </div>
                        <div class="carousel-item">
                            <img src="../assets/placeholder.jpg" class="d-block w-100" alt="A placeholder image">
                        </div>
                        <div class="carousel-item">
                            <img src="../assets/placeholder.jpg" class="d-block w-100" alt="A placeholder image">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="connect" class="bg-dark-subtle py-2 mt-4">
        <h2 class="fw-bold text-center">
            Connect with me
        </h2>
        <div class="row justify-content-center text-center">
            <p>
                <a href="#" class="px-2 icon-link"><i class="bi bi-github"></i></a>
                <a href="#" class="px-2 icon-link"><i class="bi bi-linkedin"></i></a>
                <a href="#" class="px-2 icon-link"><i class="bi bi-envelope-fill"></i></a>
            </p>
        </div>
    </div>

    <div class="container-lg">
        <h2 class="fw-bold text-center mt-3">
            Featured projects
        </h2>
        <div class="row justify-content-center text-center">
            <p class="pb-2 w-75">
                Here are some of my favorite projects I've worked on, both for my
                computer science coursework and side projects. View the source code for these and other projects on my
                <a class="link-underline link-underline-opacity-0"
                    href="https://github.com/SCM-Grievous?tab=repositories">GitHub</a>.
            </p>
        </div>
        <ProjectList />

    </div>

    <footer class="text-center bg-dark-subtle mt-3 py-3">
        <small>Created in 2024 by Nathan Moore.
        <br>Licensed under MIT.
        <br><a class="link-underline link-underline-opacity-0" href="#">View source on GitHub</a>.</small>
    </footer>
</template>

<style scoped>
a {
    color: blueviolet;
    transition: color 0.3s;
}

a:hover {
    color: rgba(138, 43, 226, 0.75);
}

.btn {
    transition: box-shadow 0.5s;
}

.btn:hover {
    box-shadow: 0 0.25rem 0.5rem rgba(0, 0, 0, 0.15);
}

.slide-fade-enter-active,
.fade-enter-active,
.button-fade-enter-active {
    transition: all 0.5s ease-out;
}

.slide-fade-leave-active {
    transition: all 0.5s ease-in;
}

.fade-enter-from {
    transform: translateX(20px);
    opacity: 0;
}

.button-fade-enter-from {
    opacity: 0;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
    transform: translateY(20px);
    opacity: 0;
}

.icon-link {
    font-size: 2rem;
}
</style>