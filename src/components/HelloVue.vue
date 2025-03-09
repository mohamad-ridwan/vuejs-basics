<!-- SFC / SINGLE FILE COMPONENT -->

<script setup>
console.info('Hello Vue')
const hello = "<h1>hello vue</h1>"
const buttonDisabled = false

const employeesData = [
    { name: 'Iwan' },
    { name: 'Dapur' },
    { name: 'Bayu' },
]

const data = {
    id: 'hello',
    class: 'hello'
}
function helloFunc() {
    return 'Hello World'
}
</script>

<template>
    <h1 v-bind="data">{{ hello.toUpperCase() }}</h1>
    <h2>{{ 100 * 200 }}</h2>
    <h2>{{ helloFunc() }}</h2>
    <div :class="data.class" v-html="hello"></div>
    <div>
        {{ employeesData.map((employee)=>emlpoyee.name) }}
    </div>
    <button :disabled="buttonDisabled">This is Button</button>
</template>

<style scoped>
.hello {
    color: green;
}
</style>