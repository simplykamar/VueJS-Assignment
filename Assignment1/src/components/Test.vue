<script setup>
    import {reactive, ref} from 'vue'

    const listData = ref([])
    const formInput = ref(
        {
            id:null,
            item:'',
            isCompleted:false
        })
    let generateId = 0
    function add(){
        if (formInput.value.item.length > 0){
        formInput.value.id=generateId
        listData.value.push(formInput.value)
        generateId+=1
        formInput.value = {
            id:null,
            item:'',
            isCompleted:false
        }
    }
    }
    function removeItem(id){
        console.log(id)
        listData.value = listData.value.filter(item=>item.id!==id)
    }
    function markCompleted(id){
        console.log(listData.value)
        listData.value.forEach(item=>
            {
                if (item.id===id){
                    item.isCompleted = !item.isCompleted
                }
            }
        )
        console.log(listData.value)
    }
</script>

<template>
    <div class="container">
        <div class="container-wrapper">
        <header>
            <nav>
                <div class="navbar-brand">Todo App</div>
            </nav>
        </header>
        <main>  
            <div class="main-content">
                <ul class="task-items">
                    <li class="task-item" v-for="item in listData">
                        <div v-on:click="markCompleted(item.id)" v-bind:style="{fontSize:'14px', color:'blue',cursor:'pointer'}">Done</div> 
                        <div v-if="item.isCompleted"><s>{{item.item}}</s></div> 
                        <div v-else>{{item.item}}</div> 
                        <div v-on:click="removeItem(item.id)" v-bind:style="{fontSize:'14px', color:'red',cursor:'pointer'}">Delete</div></li>
                </ul>
                <input v-model="formInput.item"/><br>
                <button class="new-button" v-on:click="add">+ Add task</button>
            </div>
        </main>
    </div>
    </div>
</template>

<style scoped>

.container{
    padding:50px 0px;
}
.container-wrapper{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    background-color: white;
}
    header > nav{
        display:flex;
        align-items: center;
        padding: 0 50px;
        width:100%;
        height:50px;
        background-color: rgb(175,126,235);
        border-radius: 10px;
        color:white;
        font-size: 32px;
    }
.task-item{
    display:flex;
    justify-content:space-between;
    font-size: 20px;
    list-style:none;
    margin-top:15px;
    text-transform: capitalize;
}
.new-button{
    background-color: rgb(175,126,235);
    color:white;
    font-size: 18px;
    border: 0;
    padding:10px;
    border-radius:10px;
    margin-top:20px;
    cursor:pointer
}
input{
    height: 30px;
}
</style>