<!-- PROVIDE & INJECT -->

<script setup>
import { provide, reactive } from 'vue';
import Profile from './Profile.vue';
import ProfileAddress from './ProfileAddress.vue';

const profile = reactive({
    name: 'Eko',
    email: 'eko@test.com'
})

provide('profile', profile);
</script>

<template>
    <input type="text" v-model="profile.name" placeholder="name"/>
    <Profile />
    <ProfileAddress />
</template>

<style scoped>
h1 {
    color: #42b983;
}
</style>