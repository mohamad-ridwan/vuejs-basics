<!-- PROVIDE & INJECT -->

<script setup>
import { inject } from 'vue';

const profile = inject('profile');
</script>

<template>
    <h1>Profile</h1>
    <p>Name : {{ profile.name }}</p>
    <p>Email : {{ profile.email }}</p>
</template>

<style scoped>
h1 {
    color: #42b983;
}
</style>