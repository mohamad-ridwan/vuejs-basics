<!-- PROVIDE & INJECT -->

<script setup>
import { inject } from 'vue';

const profile = inject('profile');
</script>

<template>
    <h1>Profile Address : {{ profile.name }}</h1>
    <p>Address ...</p>
</template>

<style scoped>
h1 {
    color: #42b983;
}
</style>