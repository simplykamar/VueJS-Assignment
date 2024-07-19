<script setup>
    import {ref} from 'vue'
    const name =  ref('')
</script>
<template>
    <main>
        <h1>Hello Vue My name is: {{ name }}</h1>
        <input v-bind:value="name" v-on:input="event=>name=event.target.value"/>
    </main>
</template>

<style scoped>
    main{
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column
    }
    main > h1{
        color: red
    }
</style>