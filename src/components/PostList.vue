<template>
  <div v-if="posts.length>0">
    <h3>UserList</h3>

    <post-item
        @remove="$emit('remove',post)"
        :post="post"
        :key="post.id"
        v-for="post in posts"/>
  </div>
  <h2  v-else style="color:red">
    no posts
  </h2>
</template>

<script>
import PostItem from "@/components/PostItem.vue";

export default {
  name: "PostList",
  components:{PostItem},
  props: {
    posts: {
      type: Array,
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