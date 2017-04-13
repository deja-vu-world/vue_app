<template>
  <li class="list-group-item">
    <div class="handle">
      <a href="javascript:;" @click="delComment">删除</a>
      <a href="javascript:;" @click="delComment2">删除2</a>
    </div>
    <p class="user"><span >{{comment.name}}</span><span>说:</span></p>
    <p class="centence">{{comment.content}}</p>
  </li>
</template>

<script>
export default {
  props: ['comment', 'remove', 'index'],
  methods: {
    delComment (index) {
      const name = this.comment.name
      if (window.confirm(`确定删除${name}吗?`)) {
        this.remove(this.index)
      }
    },
    delComment2 (index) {
      const name = this.comment.name
      if (window.confirm(`确定要删除${name}吗?`)) {
        this.remove(this.index)
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  li {
    transition: .5s;
    overflow: hidden;
  }

  .handle {
    width: 40px;
    border: 1px solid #ccc;
    background: #fff;
    position: absolute;
    right: 10px;
    top: 1px;
    text-align: center;
  }

  .handle a {
    display: block;
    text-decoration: none;
  }

  .list-group-item .centence {
    padding: 0px 50px;
  }

  .user {
    font-size: 22px;
  }
</style>
