<template>
  <form @submit.prevent>
    <h4>post create</h4>
    <my-input
        v-model="post.title"

        type="text"
        placeholder="name"/>
    <my-input
        v-model="post.body"
        type="text"
        placeholder="desctiption"/>
    <my-button class="input" @click="createPost" style="align-self: flex-end">add post</my-button>
  </form>

</template>

<script>

import MyInput from "@/components/UI/MyInput.vue";

export default {
  name: "PostList",
  components: {MyInput},

  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  }, methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    }
  }
}
</script>

<style scoped>

</style>