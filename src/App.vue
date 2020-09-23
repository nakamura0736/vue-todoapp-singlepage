<template>
  <div>
    <b-container class="mt-5">
      <h3>My TODO</h3>
      <b-form inline>
        <label class="sr-only" for="inline-form-input-name">Todo</label>
        <b-input
          v-model = "newTodo"
          id="inline-form-input-name"
          class="mb-2 mr-sm-2 mb-sm-0"
          placeholder="Input here.."
        ></b-input>
        <b-button variant="success"  v-on:click="addTodo()">ADD</b-button>
      </b-form>

      <h5 class="mt-5">ToDo List</h5>
      <b-list-group>
        <b-list-group-item v-for="(todo, i) in todos" v-bind:key="i" class="list-group-item d-flex justify-content-between align-items-center">
          {{ todo }}
          <b-button variant="success" v-on:click="deleteTodo(i)">DELETE</b-button>
        </b-list-group-item>
      </b-list-group>
    </b-container>
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


