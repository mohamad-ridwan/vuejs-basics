<!-- component instance -->

<script setup>

const { counter, name, increment } = defineProps({
    counter: Number,
    name: String,
    increment: Number
})

// menerima props function / event dengan defineEmits
// const emits = defineEmits(['click'])

// function buttonClick() {
//     emits('click', increment)
// }

// perlu di defineOptions agar bisa menggunakan $emit pada button
// karena pada component ini menggunakan single element, seperti <div>
// dan di div juga merupakan element yang menyediakan event click
defineOptions({
    inheritAttrs: false
})

</script>

<template>
    <div>
        <h1>Counter {{ name }} : {{ counter }}</h1>
        <!-- instance attributes components -->
        <button @click.stop="$emit('click', increment)">Increment {{ name }}</button>
    </div>
</template>

<style scoped>
button {
    margin-top: 10px;
}
</style>