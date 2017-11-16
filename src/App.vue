 
<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <router-view/> -->
    <todo-list v-bind:todos="todos"></todo-list>
    <!-- <create-todo v-on:create-todo="addTodo"></create-todo> -->
    <create-todo v-on:create-todo="addTodo"></create-todo>
  </div>
</template>

<script>
/* eslint-disable */ 
import TodoList from './components/TodoList'
import CreateTodo from './components/CreateTodo'

export default {
  name: 'app',
  components: {
    // Add a reference to the TodoList component in the components property
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos : [{
          title: 'Todo A',
          project: 'Project A',
          done: false
      },
      {
          title: 'Todo B',
          project: 'Project B',
          done: true
      },
      {
          title: 'Todo C',
          project: 'Project C',
          done: false
      },
      {
          title: 'Todo D',
          project: 'Project D',
          done: true
      }]
    };
  },
  methods: {
    addTodo(title) {
      console.log(title);
      this.todos.push(title);
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
