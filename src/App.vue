<template >
<div id="app">
  <TodoList v-bind:todos="todos" v-on:del-todo="deleteTodo" />
</div>
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'App',
  components: {
    TodoList  
  },
  data(){
    return{
      todos: [
        {
          id:1,
          title:"Todo one",
          completed:false
        },
        {
          id:2,
          title:"Todo Two",
          completed:true
        },
        {
          id:3,
          title:"Todo three",
          completed:false
        },
        {
          id:4,
          title:"Todo four",
          completed:true
        },
        {
          id:5,
          title:"Todo five",
          completed:true
        }
      ]
    }
  },
methods:{
  deleteTodo(id){
    this.todos=this.todos.filter(todo => todo.id!==id)
  }
}
} 
</script>

<style>
*{
  box-sizing : border-box;
  margin:0;
  padding:0;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
</style>
