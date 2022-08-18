<template>
    <div :class="[reminder ? 'reminder' : 'task']">
      <div>
          <h4>
            {{text}}
            <span @click="deleteTask(id)">&times;</span>
        </h4>
        <p>{{day}}</p>
      </div>
      
    </div>
</template>


<script>
export default{
    name:"Task",
    props:{
        text:String,
        day:String,
        reminder:Boolean,
        id:Number
    }, 
    methods:{
        deleteTask(id){
            this.$emit("delete-task",id);
        }
    },
    emits:['']
}
</script>

<style scoped>
    
    .reminder{
        border-left: 5px solid green;
        padding: 0 0 0 19px;
    }
    .task{
        padding: 0 0 0 19px;
        border-left: 5px solid red;
        
    }
</style>