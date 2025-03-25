<script setup>
import { ref } from 'vue'

const title = ref('My Blog Post')
const content = ref('This is the content of the blog post.')
</script>

<template>
    <h1>Blog</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi repellendus dignissimos minus, veritatis eum esse dicta, quisquam culpa, laudantium enim pariatur quia quibusdam hic accusamus eaque tenetur eligendi amet doloremque.</p>
</template>

<style scoped>
h1 {
    color: #333;
}

p {
    font-size: 16px;
}
</style>