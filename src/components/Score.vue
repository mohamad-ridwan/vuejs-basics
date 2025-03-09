<script setup>
import { ref } from 'vue'

const score = ref(60)

function increaseScore() {
    score.value++
}
</script>

<template>
    <div v-show="score">
        <h1>Score is: {{ score }}</h1>
    </div>
    <div v-if="score > 90">
        <h1>Score: {{ score }}</h1>
    </div>
    <div v-else-if="score > 70">
        <h1>Good Score: {{ score }}</h1>
    </div>
    <div v-else>
        <h1>Bad Score: {{ score }}</h1>
    </div>
    <button @click="increaseScore">Increase Score</button>
</template>

<style scoped>
h1 {
    color: #42b983;
}
button {
    margin-top: 10px;
}
</style>