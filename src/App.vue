<template>
  <div>
    <h3>My TODO</h3>
      <input v-model="newTodo" placeholder="Input here..">
      <button v-on:click="addTodo()">ADD</button>
      <h5>ToDo List</h5>
      <ul>
        <li v-for="(todo, i) in todos" v-bind:key="i">
          {{ todo }}
          <button v-on:click="deleteTodo(i)">DELETE</button>
        </li>
      </ul>
  </div>
</template>

<script>
export default {
  data(){
    return {
      todos: [],
      newTodo: ""
    }
  },
  methods: {
    addTodo(){    
      if (this.newTodo === "" ) return
      this.todos.push(this.newTodo)
      this.newTodo = ""
      console.log(this.todos)
    },
    deleteTodo(i) {
      this.todos.splice(i, 1)
    }
  }
}
</script>


