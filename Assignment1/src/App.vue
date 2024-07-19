<script setup>
    import Button from './components/Button.vue'

    function childEventHandler(params) {
        console.log("clicked")
        alert("clicked")
    }
</script>

<template>
    <Button v-on:custome-event="childEventHandler"  backgroundColor="black" color:="white" text="It is dark" />
</template>
