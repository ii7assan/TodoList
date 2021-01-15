<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to my ToDoList App"/> -->
    <!-- {{msg}} -->
    <Header />
    <AddtoDo v-on:add-todo="addtodo"/>
    <Todos v-bind:todos="todos"  v-on:del-todo="deleteTodo" />
  </div>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Header from './components/layout/header';
import Todos from './components/Todos';
import AddtoDo from './components/AddtoDo';
export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddtoDo
  },
  data() {
    return {
      isediting : false,
      todos : [
        {
          id:1,
          title: "todo one",
          completed: false
        },
        {
          id: 2,
          title: "todo two",
          completed: true
        },
        {
          id:3,
          title: "todo three",
          completed : false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addtodo(newTodo) {
        this.todos = [...this.todos , newTodo]
    },
    edittodo(id,todo){
      this.todo = todo;
      this.selectedindex = id;
      this.isediting = true;

    }
  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
#app img {
  width: 150px;
  height: 150px;
} */
*{
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
.btn:hover{
  background: #666;
}
</style>
