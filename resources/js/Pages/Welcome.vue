<script setup>
import { Head, Link } from "@inertiajs/vue3";
import FrontendLayout from "@/Layouts/Frontend.vue";
import Hero from "@/Components/Frontend/Hero.vue";
import Promote from "@/Components/Frontend/Promote.vue";
import About from "@/Components/Frontend/About.vue";
import Skills from "@/Components/Frontend/Skills.vue";
import Portfolio from "@/Components/Frontend/Portfolio.vue";
import Services from "@/Components/Frontend/Services.vue";

defineProps({
    skills: Object,
    projects: Object,
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
        <!-- Portfolio section  -->
        <Portfolio :skills="skills" :projects="projects" />
        <!-- Services section  -->
        <Services />
    </FrontendLayout>
</template>
