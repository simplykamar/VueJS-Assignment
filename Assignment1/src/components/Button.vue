<script setup>
    const props = defineProps({
        color:{
            default:"white"   
        },
        backgroundColor:{
            default:"#0069D9"
        },
        text:{
            default:"Primary",
            required:true
        }
        
    })

</script>
<template>
    <div class="button-container">
        <h1>Reusable base button</h1>
        <button v-on:click="$emit('custome-event')" v-bind:style="{backgroundColor:backgroundColor,color:color}">{{props.text}}</button>
    </div>
</template>

<style scoped>
   button{
    width:80px;
    height:40px;
    cursor:pointer
   }
   .button-container{
    display:flex;
    justify-content:center;
    align-items:center;
    flex-direction:column
   }
</style>