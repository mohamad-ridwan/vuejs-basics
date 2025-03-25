<script setup>
import { ref } from 'vue';

const product = defineProps({
    id: {
        type: Number,
        required: true
    },
    name: {
        type: String,
        required: true,
        validator: (value) => {
            return value.trim().length !== 0
        }
    },
    price: {
        type: Number,
        required: true,
        validator: (value) => {
            return value > 0
        }
    }
})
</script>

<template>
    <h1>Product</h1>
    <p>Id : {{ product.id }}</p>
    <p>Name : {{ product.name }}</p>
    <p>Price : {{ product.price }}</p>
</template>

<style scoped>
h1 {
    font-size: 2em;
    margin-bottom: 0.5em;
}

p {
    margin: 0.5em 0;
}
</style>