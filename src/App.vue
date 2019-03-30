<template>
  <div id="app">
    <h1 class="ui dividing centered header">CSA Karaoke Night</h1>
    <div class='ui three column centered grid'>
      <div class='column'>
        <todo-list v-bind:todos="todos"></todo-list>
        <create-todo v-on:create-todo="createTodo"></create-todo>
      </div>
    </div>
  </div>
</template>

<script>
import sweetalert from 'sweetalert';
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'app',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [],
    };
  },
  methods: {
    createTodo(newTodo) {
      this.todos.push(newTodo);
      sweetalert('Success!', 'Your song is added to queue!', 'success');
    },
  },
};
</script>
