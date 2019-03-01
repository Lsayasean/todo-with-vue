<template>
  <div id="app">
    <Todo 
    v-bind:todos='todos'
    v-on:del-todo="deleteTodo"
    />
    <AddToDo 
    v-on:add-todo='addTodo'
    />
  </div>
</template>

<script>
import Todo from './components/Todo'
import AddToDo from './components/AddToDo'

export default {
  name: 'app',
  components: {
    Todo,
    AddToDo
  },
  data(){
    return {
      // this is the state/data
      todos: [
        {
          id: 1,
          title: 'Code',
          completed: false
        },
        {
          id: 2,
          title: 'Code again',
          completed: false
        },
        {
          id: 3,
          title: 'Get ready for FIRST SOFTWARE JOB',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo]
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
