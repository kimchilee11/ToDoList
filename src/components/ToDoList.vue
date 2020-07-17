<template>
    <div class="container">
        <header>
            <h1 class="todolist-title">
               ToDoList
            </h1>
            <form action="" class="todolist">
                <b-form-input type="text" class="todolist-create" placeholder="Nhap ten cua ban" v-model="item" > </b-form-input>
                <b-button class="todolist-button-add" id="addName" @click.prevent="addName" >Add Name</b-button>
            </form>
        </header>
        <div class="todolist-obj"  v-for=" (item,index) in listNames" v-bind:key=item.id >
                <div v-if="!item.edit" class="todolist-obj-content">{{ item.name}} </div>
                <b-form-input v-else type="text" v-model="item.name" 
                @blur="doneEdit(item)"
                @keyup.enter="doneEdit(item)"
                class="todolist-edit-content"></b-form-input>
            <itemList  class="todolist-button"  @onDel="deleting(index)"  @onEdit="editing(item)"/>
        </div>
    </div>
</template>

<script>
import itemList from './itemList'
// import Vue from 'vue'
// import 'bootstrap/dist/css/bootstrap.css'
// import 'bootstrap-vue/dist/bootstrap-vue.css'
// import { BootstrapVue, IconsPlugin } from 'bootstrap-vue'
export default {
    data(){
        return {
            listNames: [
                {
                    id: 1,
                    name: "name1",
                    edit: false
                },
                {
                    id: 2,
                    name: "name2",
                    edit: false

                },
                {
                    id:3,
                    name: "name3",
                    edit: false

                },
                {
                    id:4,
                    name: "name4",
                    edit: false

                },
                {
                    id:5,
                    name: "name5",
                    edit: false

                }
            ] ,
            item : '',
            idName: 6
        }
    },
    components:{
        itemList
    },
    methods:{
        addName(){
            this.listNames.push({
            name: this.item,
            id : this.idName
            })
            this.item='',
            this.idName++
        },
        // todoDel(index){
        //     this.
        // },
        deleting(index){
            this.listNames.splice(index,1)
        },
        editing(index){
            index.edit=true
        },
        doneEdit(index){
            index.edit=false
        }
}
}
</script>

<style>
.todolist-title{
    padding:25px  20px;
    font-size: 90px;
}
.todolist-obj{
    margin: 10px;
    padding: 10px;
}
.todolist-obj-content {
    display: inline;
    margin: 10px;
    padding:  10px;
}
.todolist-button,.todolist-create,.todolist-edit-content{
    display: inline;
    width: 40%;
}

</style>