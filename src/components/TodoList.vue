<template>
  <div>
    <ul>
        <li v-for="(todoItem,index) in todoItems" v-bind:key="todoItem">
            <i> </i>
            {{todoItem.item}}
           
            <span class="removeBtn" v-on:click="removeTodo(todoItem,index)">
                <i class="fas fa-trash-alt">휴지통</i>
            </span>
        </li>
        <!--<li>hi</li>
        <li>hello</li>
        <li>bye</li>
        <li>adfaff</li>-->
    </ul>
  </div>
</template>

<script>
export default {
    data:function(){
        return{todoItems:[]}
    },
    methods:{
        removeTodo :function(todoItem, index){
            console.log(todoItem, index);
            localStorage.removeItem(todoItem);
            this.todoItems.splice(index,1)
        }
    },
    created:function(){
        if(localStorage.length>0){
            for(var i=0; i<localStorage.length; i++){
                    if(localStorage.key(i)!=='loglevel:webpack-dev-server'){
                
               this.todoItems.push(JSON.parse(localStorage.getItem(localStorage.key(i))));
                //console.log(localStorage.key(i))
                    }
                }
            }
        }
    }

</script>

<style>

</style>