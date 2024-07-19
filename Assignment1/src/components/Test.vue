<script setup>
    import {ref} from 'vue'
    
    const listItems = ref([])
    const itemValue = ref('')
    
    function addItem() {
        if (itemValue.value.length > 0){
            console.log("add fn")
            listItems.value.push(itemValue.value)
            itemValue.value=''
            }
    }
    function deleteList(itemIndex){
        if (listItems.value.length >= itemIndex){
            listItems.value.splice(itemIndex,1)
        }
    }
</script>
<template>
    <main>
        <h1>Add Item</h1>
        <input v-on:input="event=>itemValue=event.target.value" v-bind:value="itemValue"/>
        <button v-on:click="addItem">Add Item</button>
        <ul v-if="listItems.length > 0">
            <li v-for="(item,index) in listItems" v-bind:key="item">
                <div>{{item}}</div>
                <div class="list-item-delete" >
                    <a href="#" v-on:click="deleteList(index)"> Delete </a>
                </div>
            </li>
        </ul>
    </main>
</template>

<style scoped>
    main{
        display:flex;
        justify-content:center;
        align-items:center;
        flex-direction:column;
    }
    main > input{
        width:200px
    }
    main > button{
        margin: 10px
    }
    main  li{
        font-size:18px; 
        text-transform:capitalize;
        border:1px solid black;
        width:250px;
        text-align:center;
        margin-top:10px;
        list-style:none;
    }
    .list-item-delete{
        display:flex;
        justify-content:right;
    }
    .list-item-delete a{
        text-decoration:none
    }
    .list-item-delete a:hover{
        color:green
    }
    h1{
        text-align: center;
    }
</style>