<!-- COMPONENT SLOT -->
<!-- menambahkan slot lebih dari 1 dalam component -->

<script setup>
import { ref, useSlots } from 'vue';

const { title } = defineProps({
    title: String
});

// pengecekan slots
// conditional slots
// const slots = useSlots()

const counter = ref(0);
</script>

<template>
    <!-- karena slots merupakan component instance / attribute yang sudah disediakan -->
    <!-- maka bisa langsung mengaksesnya seperti $slots.header dll -->
    <!-- kalau untuk akses di javascript bisa seperti mengakses di instance yaitu this.slots -->
    <div v-if="$slots.header">
        <slot name="header" :counter="counter">
            <h1>Default header</h1>
        </slot>
    </div>
    <div v-if="$slots.default" class="container">
        <slot name="default" :counter="counter">
            <p>Anda belum mengisi contentnya</p>
        </slot>
    </div>
    <div v-if="$slots.footer" :counter="counter">
        <slot name="footer">
            <p>Default footer</p>
        </slot>
    </div>
    <div>
        <button @click="counter++">Increment Counter</button>
    </div>
</template>

<style scoped>
.container {
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
}
</style>