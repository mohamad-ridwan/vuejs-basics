<!-- FALLTHROUGH ATTRIBUTE COMPONENT -->
<!-- USING SLOT COMPONENT -->

<script setup>
import Container from './Container.vue';
import MyButton from './MyButton.vue';

const handleClick = () => {
    alert('Button clicked!');
};
</script>

<template>
    <Container title="Contoh Button">
        <template #header="attributes">
            <h1>Button App {{ attributes.counter }}</h1>
        </template>
        <template v-slot:default="attributes">
            <MyButton class="button" @click="handleClick" :name="attributes.counter" contoh="Kurniawan" />
        </template>
        <template #footer>
            <p>Copyright 2025</p>
        </template>
    </Container>
</template>

<style scoped>
.button {
    background-color: #4CAF50;
    /* Green */
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border-radius: 12px;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: #45a049;
}
</style>