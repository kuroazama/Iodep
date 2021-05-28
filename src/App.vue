<template>
  <div>
    <div id="header"></div>
    <div id="main-container">
      <h2>Todos</h2>
      <Todos v-bind:todoslist="copytodos" v-on:delete-todo="deleteTodo"/>
    </div>
  </div>
</template>

<script>
import search from './components/search'
import Todos from './components/Todos'
import Todoadd from './components/Todoadd'
export default {
  name: 'App',
  components:  {
    search,Todos,Todoadd
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
      this.copyTodos = [...this.todos];
    },
  },
  data(){
    return {
      todos:[
        {
          id: 0,
          title:'comprar la cena',
          completed: false 
        },
        {
          id: 1,
          title:'sacar a pasear al perro',
          completed: false 
        },
        {
          id: 2,
          title:'jugar al warzone',
          completed: false 
        },
        {
          id: 3,
          title:'Lo que sea',
          completed: false 
        },
      
      ],
      copytodos:[]
    }
  },
  created(){
    this.copytodos= [...this.todos];
  }
}
 
</script>
<style>
*{
  box-sizing: border-box;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.5em;
  padding: 0;
  margin: 0;
}
#main-container{
  border: solid 1px #ccc;
  width: 600px;
  margin: 100px auto;
}
#header{
  background: black;
  padding: 10px;
}
h2{
  padding: 0 10px;
}
</style>