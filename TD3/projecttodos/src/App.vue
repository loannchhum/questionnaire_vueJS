<script>
import TodoItem from './components/TodoItem.vue';

let data = [
    { id: "1", text: 'Apprendre ES6 ', checked: true },
    { id: "2", text: 'Apprendre Vue ', checked: false },
    { id: "3", text: 'Faire un projet magnifique ', checked: false }
    ]

export default {
    data() {
      return {todos:[
    { text: 'Apprendre ES6 ', checked: true },
    { text: 'Apprendre Vue ', checked: false },
    { text: 'Faire un projet magnifique ', checked: false }
    ]};
    },
    methods:{
        remove(index) {
          this.todos.splice(index,1);
        }
    },

    components : { TodoItem }
}

</script>

<template>
  <h1>Todos</h1>
  <ul>
    <button @click = remove()>Ajouter une tâche</button >
    <TodoItem v-for="todo in todos" :todo="todo" @remove="remove(todo.id)"/>
  </ul>
</template>

<style scoped>
  div > * {
    padding: 1em;
  }
</style>
