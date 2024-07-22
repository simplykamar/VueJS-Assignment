<script setup>
    import {ref} from 'vue'

    const customerData = ref([])//[{id:1,firstName:"kamar",lastName:"alam",address:"address"},{},{}]
    const formInput = ref({
        id:null,
        firstName:'',
        lastName:'',
        address:''
    })
    const generateId = ref(0)

    function addItem() {
        formInput.value.id = generateId.value
        customerData.value.push(formInput.value)
        formInput.value = {
            id:null,
            firstName:'',
            lastName:'',
            address:''
            }
        generateId.value+=1
    }
    function deleteItem(id) {
        console.log(id)
        customerData.value = customerData.value.filter((item)=>item.id!==id)
    }
</script>

<template>
    <main>
        <h2>Customer Details</h2>
        <div>
            <label for="">First Name</label>
            <input type="text" v-model="formInput.firstName" placeholder="Enter First Name"/>
            <label for="">Last Name</label>
            <input type="text" v-model="formInput.lastName" placeholder="Enter Last Name"/>
            <label for="">Address</label>
            <input type="text" v-model="formInput.address" placeholder="Enter Address"/>
            <button v-on:click="addItem">ADD</button>
        </div>
        <div>
            <table>
                <tr v-for="data in customerData">
                    <td>{{data.firstName}}</td>
                    <td>{{data.lastName}}</td>
                    <td>{{data.address}}</td>
                    <td v-on:click="deleteItem(data.id)"><a href="#">x</a></td>
                </tr>
            </table>
        </div>
    </main>
</template>

<style scoped>
    main{
        margin:10px
    }
    button{
        margin-left:10px;
        width:70px;
        height:30px
    }
    table{
        margin-top:50px;
        width:75%;
        border:1px solid black
    }
    td{
        margin-top:10px;
        border:1px solid black;
        text-transform:capitalize;
        background-color:yellow;
    }
</style>