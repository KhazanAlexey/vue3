<template>
  <div class="post">
    <div><strong>название : </strong>{{ post.title }}</div>
    <div><strong>описание : </strong>{{ post.body }}</div>
    <div>
      <my-button>change</my-button>
      <my-button @click="$emit('remove',post)">delete</my-button>
    </div>
  </div>
</template>

<script>

export default {
  name: "PostItem",

  props: {
    post: {
      type: Object,
      required:true
    }
  }
}
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid green;
  margin-top: 15px;
}
</style>