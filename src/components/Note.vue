<!-- TEMPLATE REFS -->
<!-- Ref dalam v-for -->
<!-- LIFE CYCLE HOOKS -->

<script setup>
import { onBeforeMount, onMounted, onUpdated, reactive, ref, useTemplateRef } from 'vue';

const notes = reactive([])
const note = ref('');
const noteInput = useTemplateRef('noteInput')
const noteList = useTemplateRef('noteList')

const addNote = () => {
    notes.push(note.value)
    note.value = ''
    noteInput.value.focus()
    if (noteList.value) {
        noteList.value.forEach((li) => {
            console.log(li.textContent)
        })
    }
};

onBeforeMount(() => {
    console.log('onBeforeMount')
})
onMounted(() => {
    console.log('onMounted')
})
onUpdated(() => {
    console.log('onUpdated')
})
</script>

<template>
    <h1>Buat Note</h1>
    <div>
        <input ref="noteInput" type="text" v-model="note" placeholder="Enter a note" />
        <button @click="addNote">Add Note</button>
    </div>

    <h1>Daftar Note</h1>
    <ul>
        <li v-for="note in notes" ref="noteList">{{ note }}</li>
    </ul>
</template>

<style scoped></style>