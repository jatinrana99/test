<template>
    <div>Form
    <p>Enter Something</p>
        <i>Press enter</i>
        <br/>
        <form v-on:submit.prevent>
            <input v-on:keypress="submit" type="text" v-model="text" />
        </form>
    </div>
</template>

<script>
export default {
    name:`AddForm`,
    data(){
        return{
            text:""
        }
    },

    // adding watchers
        watch: {
            name: function(newName){
                console.warn("watch ", newName);
                this.text = newName;
            }
        },

        props:{
            name:{
                type:String,
                require:true
            },
            editIndex:{
                type: Number,
                require:true
            }
        },

    methods:{
        submit: function(e) {
      if (e.keyCode === 13) {
        // this.$emit("submit-item",this.name);
        // this.name="";
      console.log(this.editIndex);
      
        
        if(this.editIndex !== -1){

            // eslist-disable the next line
            console.warn("edit item");
            this.$emit("edit-item",{
                name:this.text,
                editIndex: this.editIndex
            });
        }

        else{
            this.$emit("submit-item", this.text);
        }
        this.text="";
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