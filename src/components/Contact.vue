<script setup>
import { reactive, ref } from 'vue'
import ContactForm from './ContactForm.vue'
import ContactList from './ContactList.vue'

const title = ref('Contact Us')
const message = ref('Feel free to reach out to us!')

const updateMessage = () => {
    message.value = 'Thank you for contacting us!'
}

const contact = reactive({
    name: "",
    email: "",
    age: 0,
    type: "Regular",
    complain: false,
    message: ""
})
</script>

<template>
    <ContactForm v-model="contact"/>
    <ContactList
        v-model:name.uppercase="contact.name"
        v-model:email="contact.email"
        v-model:age="contact.age"
        v-model:type="contact.type"
        v-model:complain="contact.complain"
        v-model:message="contact.message"
    />
</template>

<style scoped>
h1 {
    color: #42b983;
}
</style>