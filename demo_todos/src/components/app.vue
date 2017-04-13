<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <todo-header :add-todo="addTodo"></todo-header>
      <todo-main :todos="todos"></todo-main>
      <todo-footer :todos="todos"></todo-footer>
    </div>
  </div>
</template>

<script>
  import header from './header'
  import main from './main'
  import footer from './footer'
  export default{
    data () {
      return {
        todos: [
          {text: '抽烟', isDone: false},
          {text: '喝酒', isDone: false},
          {text: '烫头', isDone: false}
        ]
      }
    },
    methods: {
      addTodo (todo) {
        this.todos.unshift(todo)
      },
      removeTodo (todo) {
        this.todos.$remove(todo)
      }
    },
    events: {
      // 变量名，也可以用字符串的形式命名
      'remove-todo': function (todo) {
        this.todos.$remove(todo)
      }
    },
    components: {
      'todo-header': header,
      'todo-main': main,
      'todo-footer': footer
    }
  }
</script>

<style>
  /*app*/
  .todo-container {
    width: 600px;
    margin: 0 auto;
  }
  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }
</style>

