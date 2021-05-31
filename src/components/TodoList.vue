<template>
  <div>
    <input type="text" v-model="newTodoItem">
    <button v-on:click="addTodo">add</button>
  </div>
</template>

<script>
export default {
    data: function(){
        return{
            newTodoItem:""
        }
    },
    methods:{
        addTodo:function(){
            localStorge.setItem()
        }
    }
}
</script>

<style>

</style>