<!-- TEMPLATE REFS -->

<script setup>
import { ref } from 'vue';

const note = ref('');
const noteInput = ref(null);

const saveNote = () => {
    console.log(note.value);
    noteInput.value.focus();
};
</script>

<template>
    <div>
        <input ref="noteInput" v-model="note" placeholder="Enter a note" />
        <button @click="saveNote">Save Note</button>
    </div>
</template>

<style scoped>

</style>