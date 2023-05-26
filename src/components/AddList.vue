<template>
    <div>
        <FormAdd v-on:submit-item="submit"/>
        <ul>
            <li v-for="(item,index) in items" v-bind:key="index">
            <span>{{ item }}</span>
            <div>
                <i class="fa-solid fa-pen-to-square" v-on:click.prevent="editItem(index)"></i>
                <i class="fa-solid trash" v-on:click.prevent="deleteItem(index)"></i>
            </div>
            </li>
        </ul>
    </div>
</template>

<script>
import FormAdd from './FormAdd.vue'

export default {
    name:`AddList`,
    components:{
        FormAdd
    },
    data(){
        return{
            items:[]
        }
    },
    methods:{
        submit:function(name){
            this.items.push(name);
        },
    //     editItem: function(index) {
    //         this.editIndex=index;
    //         this.name=this.items[index];
    // },
    deleteItem: function(index) {
        this.items.splice(index,1);
    }
    }
  }

</script>