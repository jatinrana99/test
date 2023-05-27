<template>
    <div>
        <!-- <FormAdd v-on:submit-item="submit"/> -->
        <FormAdd v-bind:edit-index="editIndex" 
                 v-bind:name="name"
                 v-on:edit-item="edit"
                 v-on:submit-item="submit">
         </FormAdd>
        <ul>
            <li v-for="(item,index) in data" v-bind:key="index">
            <span>{{ item }}</span>
            <div>
                <i class="fa-solid fa-pen-to-square" v-on:click.prevent="editItem(index)"></i>
                <i class="fa-solid fa-trash" v-on:click.prevent="deleteItem(index)"></i>
            </div>
            </li>
        </ul>
    </div>
</template>

<script>
import FormAdd from './FormAdd.vue'
// import Vue from 'vue'

export default {
    name:`AddList`,
    components:{
        FormAdd
    },
    data(){
        return{
            data:[],
            name:"",
            editIndex:-1
        }
    },
    methods:{
        submit:function(name){
            this.data.push(name);
            this.name="";
        },
    deleteItem: function(index) {
        this.data.splice(index,1);
    },
        edit:function(obj){
            var{name,editIndex} = obj;
            // eslist disable the next Line
            console.log("hello from edit");
            console.log("actual edit", name , editIndex);
            // Vue.set(this.data,editIndex, name);
            this.data.splice(editIndex,1,name);
            this.name="";
            this.editIndex =-1;
        },
        editItem:function(index){
            console.log("edit index");
            this.editIndex= index;
            this.name = this.data[index];
        }
    }
  }

</script>