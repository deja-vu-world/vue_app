<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="comments.length===0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group" v-show="comments.length>0">
      <comment-item v-for="comment in comments" :comment="comment" :remove="remove" :index="$index"></comment-item>
    </ul>
  </div>
</template>

<script>
  import CommentItem from './CommentItem'

  export default {
    props: {
      comments: {
        type: Array,
        required: true
      },
      remove: {
        type: Function
      }
    },
    data () {
      return {

      }
    },
    components: {
      CommentItem
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .reply {
    margin-top: 0px;
  }
</style>
