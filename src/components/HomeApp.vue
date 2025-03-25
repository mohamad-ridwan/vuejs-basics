<!-- DYNAMIC COMPONENTS -->

<script setup>
import { ref } from 'vue';
import About from './About.vue';
import Blog from './Blog.vue';
import Contact from './Contact.vue';

const currentPage = ref('about')

const pages = {
    about: About,
    blog: Blog,
    contact: Contact
}
</script>

<template>
    <button @click="currentPage = 'about'">About</button>
    <button @click="currentPage = 'blog'">Blog</button>
    <button @click="currentPage = 'contact'">Contact</button>

    <!-- untuk menampilkan dynamic component -->
    <component :is="pages[currentPage]" />
</template>

<style scoped>
h1 {
    color: #42b983;
}
</style>