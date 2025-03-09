<script setup>
import { nextTick, ref } from 'vue';

let counter = ref({
    count: 0,
    name: 'Eko'
})

async function increment(){
    counter.value = {
        name: counter.value.name,
        count: counter.value.count + 1
    }
    console.log('Increment count after nextTick : ', counter.value.count)

    await nextTick()
    counter.value.count++

    await nextTick()
    counter.value.count++
}
</script>

<template>
    <div>
        <h1 id="count">Counter : {{ counter.count }}</h1>
        <button v-on:click="increment">Increment</button>
    </div>
</template>

<style scoped>
button {
    margin-top: 10px;
}
</style>