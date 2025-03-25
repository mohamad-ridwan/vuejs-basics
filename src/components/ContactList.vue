<script setup>
// model binding yang dikirim dari parent untuk props
// model options / single model / argument
// multiple model

// model modifier
const [name, nameModifiers] = defineModel('name', {
    type: String,
    get: (value)=>{
        if(nameModifiers.uppercase){
            return value.toUpperCase()
        }
        return value
    }
})
const email = defineModel('email', {
    type: String,
})
const age = defineModel('age', {
    type: Number,
})
const type = defineModel('type', {
    type: String,
})
const complain = defineModel('complain', {
    type: Boolean,
})
const message = defineModel('message', {
    type: String,
})
</script>

<template>
    <h1>Preview</h1>
    <div>
        <p>Name : {{ name }}</p>
        <p>Email : {{ email }}</p>
        <p>Age : {{ age }}</p>
        <p>Type : {{ type }}</p>
        <p>Complain : {{ complain }}</p>
        <p>Message : {{ message }}</p>
    </div>
</template>

<style scoped>
h1 {
    font-size: 24px;
    margin-bottom: 10px;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    margin-bottom: 5px;
}
</style>