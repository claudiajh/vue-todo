<template>
  <div class="Todo">
    <input v-model="newTodoText" v-on:keyup.enter="addNewTodo" placeholder="Add a todo">
    <ol>
      <li is="todolist" v-for="todo in todolist">
        <p>{{todo.title}}</p>
      </li>
    </ol>
  </div>
</template>

<script>
  export default {
    name: 'Todo',
    data() {
      return {
        todolist: [
          {
            id: 1,
            title: 'First Invasion',
          },
          {
            id: 2,
            title: 'She`s Back',
          },
          {
            id: 3,
            title: 'Evolution'
          }
        ],
        newTodoText: '',
        newTodoId: 4
      }
    },
    methods: {
      addNewTodo: function () {
        this.todolist.push({
          id: this.nextTodoId++,
          title: this.newTodoText
        });
        this.newTodoText = ''
      }
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
</style>
