<template>
    <div>Form
    <p>Enter Something</p>
        <i>Press enter</i>
        <br/>
        <form v-on:submit.prevent>
            <input v-on:keypress="submit" type="text" v-model="name" />
        </form>
    </div>
</template>

<script>
export default {
    name:`AddForm`,
    data(){
        return{
            name: " ",
            editIndex:false
        }
    },
    methods:{
        submit: function(e) {
      if (e.keyCode === 13) {
        this.$emit("submit-item",this.name);
        this.name="";
      }
        // if(this.editIndex){
        //     this.items.splice(this.editIndex,1,this.name);
        //     this.name="";
        //     this.editIndex-1;
        // }
        // else{
        //     this.items.push(this.name);
        // this.name = "";
        // }
     
      }
       }
    }

</script>