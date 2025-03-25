<!-- FALLTHROUGH ATTRIBUTE COMPONENT -->

<script setup>
import { useAttrs } from 'vue';

// const { contoh } = defineProps(['contoh'])

// jika mau di menonaktifkan attribute fallthrough
// defineOptions({
//     inheritAttrs: false
// })

// ini adalah function yang digunakan untuk mengambil semua attribute yang ada pada component
// terkecuali attribute yang di define pada component
const attribute = useAttrs()
console.log(attribute)
</script>

<template>
    <button>My Button : {{ attribute.name }}</button>
</template>

<style scoped></style>