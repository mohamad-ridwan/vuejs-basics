<script setup>
// model binding yang dikirim dari parent untuk props
// model options
// getter dan setter untuk model
const model = defineModel({
    type: Object,
    required: true,
    get: (value)=>{
        value.email = value.email.toUpperCase()
        return value
    }
})
</script>

<template>
    <form action="">
        <div>
            <label for="name">Name
                <input type="text" id="name" v-model="model.name">
            </label>
        </div>
        <div>
            <label for="email">Email
                <input type="email" id="email" v-model="model.email">
            </label>
        </div>
        <div>
            <label for="age">Age
                <input type="number" id="age" v-model="model.age">
            </label>
        </div>
        <div>
            <label for="type">Type
                <select name="type" id="type" v-model="model.type">
                    <option value="Regular">Regular</option>
                    <option value="VIP">VIP</option>
                </select>
            </label>
        </div>
        <div>
            <label for="complain">Complain
                <input type="checkbox" id="complain" v-model="model.complain">
            </label>
        </div>
        <div>
            <label for="message">Message
                <textarea name="message" id="message" v-model="model.message"></textarea>
            </label>
        </div>
    </form>
</template>

<style scoped>
/* Add your styles here */
</style>