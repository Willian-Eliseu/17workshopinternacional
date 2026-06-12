<template>
    <header>
        <nav :class="['navbar navbar-expand-xl shadow bg-principal', { 'fixed-top': fixedNavbar }]" data-bs-theme="dark">
            <div class="container">
                <a class="navbar-brand" href="/">
                    <!-- logo -->
                    <!-- <img src="@/assets/logo.png" alt="Logo" height="40" class="d-inline-block align-text-top"> -->
                    <span class="fw-bold text-light">
                        WORKSHOP INTERNACIONAL
                    </span>
                </a>
                <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav"
                    aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse justify-content-end" id="navbarNav">
                    <ul class="navbar-nav fw-bold">
                        <li class="nav-item ms-lg-2">
                            <RouterLink class="nav-link" to="/#sobre">CONVIDADOS</RouterLink>
                        </li>
                        <li class="nav-item ms-lg-2">
                            <RouterLink class="nav-link" to="/#participantes">PROGRAMAÇÃO</RouterLink>
                        </li>
                        <li class="nav-item ms-lg-2">
                            <RouterLink class="nav-link" to="/#programacao">REALIZAÇÃO</RouterLink>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';
import { RouterLink } from 'vue-router';

const fixedNavbar = ref(false);
const onScroll = () => {
    window.scrollY > 100 ? fixedNavbar.value = true : fixedNavbar.value = false;
}
onMounted(() => {
    window.addEventListener('scroll', onScroll);
})
</script>

<style scoped>

</style>