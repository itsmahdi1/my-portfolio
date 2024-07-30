<script setup>
import { Head, Link } from "@inertiajs/vue3";
import FrontendLayout from "@/Layouts/Frontend.vue";
import Hero from "@/Components/Frontend/Hero.vue";
import Promote from "@/Components/Frontend/Promote.vue";
import About from "@/Components/Frontend/About.vue";
import Skills from "@/Components/Frontend/Skills.vue";

// function handleImageError() {
//     document.getElementById('screenshot-container')?.classList.add('!hidden');
//     document.getElementById('docs-card')?.classList.add('!row-span-1');
//     document.getElementById('docs-card-content')?.classList.add('!flex-row');
//     document.getElementById('background')?.classList.add('!hidden');
// }

defineProps({
    skills: Object,
});
</script>

<template>
    <Head title="Welcome to Portfolio" />
    <FrontendLayout>
        <!-- Hero primary  -->
        <Hero />
        <!-- Promote section  -->
        <Promote />
        <!-- About section  -->
        <About />
        <!-- Skills section  -->
        <Skills :skills="skills" />
    </FrontendLayout>
</template>
