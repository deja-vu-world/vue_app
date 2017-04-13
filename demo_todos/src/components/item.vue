<template>
  <li :style="{background: bgColor}" @mouseenter="toggle(true)" @mouseleave="toggle(false)">
    <label>
      <input type="checkbox" v-model="todo.isDone" />
      <span>{{todo.text}}</span>
    </label>
    <button class="btn btn-danger" v-show="isShow" @click="delTodo">删除</button>
  </li>
</template>

<script>
  export default{
    props: ['todo'],
    data () {
      return {
        isShow: false,
        bgColor: 'white'
      }
    },
    methods: {
      toggle (isEnter) {
        if (isEnter) { // 在函数中传入过了，所以读它的值为true
          this.isShow = true
          this.bgColor = '#ddd'
        } else {
          this.isShow = false
          this.bgColor = 'white'
        }
      },
      delTodo (todo) {
        if (window.confirm(`确定要删除${this.todo.text}吗?`)) {
          this.$dispatch('remove-todo', this.todo)
        }
      }
    }
  }
</script>

<style>

</style>

