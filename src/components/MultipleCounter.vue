<!-- IMPORT COMPONENT IN COMPONENT -->

<script setup>
import { ref } from 'vue';
import Counter from './Counter.vue';
import CounterStateless from './CounterStateless.vue';

const counter1 = 'Eko'
const counter2 = 'Budi'

const counter = ref(0)

function increment(value) {
    counter.value += value
}
</script>

<template>
    <Counter :name="counter1" initial-count="100" />
    <Counter v-bind:name="counter2" initial-count="200" />

    <CounterStateless name="Joko" :counter="counter" :increment="1" v-on:click="increment" />
    <CounterStateless name="Morro" :counter="counter" :increment="2" @click="increment" />
</template>

<style scoped>
button {
    margin: 5px;
}
</style>