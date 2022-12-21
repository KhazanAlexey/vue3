<template>
  <div class="app">

    <post-form @create="createPost"/>
    <post-list
        @remove="removePost"
        :posts="posts"
        />
  </div>

</template>

<script>
import postForm from "@/components/PostForm.vue";
import postList from "@/components/PostList.vue";


export default {
  components: {
    postForm, postList
  },
  name: "App",
  data() {
    return {
      posts: [
        {id: 1, title: 'js', body: 'description post 1'},
        {id: 2, title: 'js2', body: 'description post 2'},
        {id: 3, title: 'js3', body: 'description post 3'}
      ],
    }
  },
  methods: {
    createPost(post) {

      this.posts.push(post)

    },
    removePost(post){
      this.posts=this.posts.filter(p=>p.id!==post.id)
    }

  }

}
</script>

<style>
.app {
  padding: 20px;
}

</style>