<script setup>
    import Card from './components/Card.vue'
</script>

<template>
    <Card>
        <template v-slot:header>
            <img src="https://img.freepik.com/free-photo/painting-mountain-lake-with-mountain-background_188544-9126.jpg" alt="Avatar" style="width:50%">
        </template>
        <template v-slot:title>
            <h2>Card title</h2>
        </template>
        <template v-slot:body>
            <h4>Card body</h4>
        </template>
        <template v-slot:footer>
            <p>Card footer</p>
        </template>
    
    </Card>

</template>

<style scoper>

</style>