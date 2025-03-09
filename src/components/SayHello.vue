<script setup>
import { computed, reactive, ref } from 'vue';

const person = reactive({
    firstName: "",
    lastName: ""
})

function sayHello() {
    person.firstName = document.getElementById('firstName').value
    person.lastName = document.getElementById('lastName').value
}
const fullName = computed((oldName, debug) => {
    console.log(`change old name ${oldName}`)
    return `${person.firstName} ${person.lastName}`
})

const counter = ref(0)

function changeFirstName(event) {
    person.firstName = event.target.value
}
function changeLastName(event) {
    person.lastName = event.target.value
}
</script>

<template>
    <form @submit.prevent>
        <button v-on:click="counter++" type="button">Increment {{ counter }}</button> <br>
        <input type="text" placeholder="First Name" id="firstName" @input="changeFirstName"> <br>
        <input type="text" placeholder="Last Name" id="lastName" v-on:input="changeLastName"> <br>
        <button v-on:click.prevent="sayHello" type="submit">Say Hello</button>
    </form>
    <h1>Hello {{ fullName }}</h1>
</template>

<style scoped>
h1 {
    color: #42b983;
}
</style>