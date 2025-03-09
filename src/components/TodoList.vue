<script setup>
import { ref } from 'vue';

const todos = ref([
    { id: 1, text: 'Learn Vue 3', done: false },
    { id: 2, text: 'Done True', done: true },
    { id: 3, text: 'Build a Todo App', done: false }
]);

const newTodo = ref('');

const addTodo = () => {
    if (newTodo.value.trim() !== '') {
        todos.value.push({ id: Date.now(), text: newTodo.value });
        newTodo.value = '';
    }
};
</script>

<template>
    <div>
        <h1>Todo List</h1>
        <template v-for="todo in todos">
            <ul v-if="!todo.done" :key="todo.id">
                <li v-for="(value, key) in todo">
                    {{ key }}: {{ value }}
                </li>
            </ul>
        </template>
        <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new todo" />

        <div v-for="n in 10">
            <h1>Hello {{ n }}</h1>
        </div>
    </div>
</template>

<style scoped>
h1 {
    font-size: 2em;
    margin-bottom: 0.5em;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    background: #f9f9f9;
    margin: 0.5em 0;
    padding: 0.5em;
    border-radius: 4px;
}

input {
    padding: 0.5em;
    font-size: 1em;
    border: 1px solid #ccc;
    border-radius: 4px;
}
</style>