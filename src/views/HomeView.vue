<template>
  <div class="home">
    <div v-if="error"> {{ error }} </div>
    <div v-if="posts.length">
    <PostList :post="posts" />
    </div>
    <div v-else> Loading... </div>
  </div>
</template>

<script>
import PostList from '../components/PostList.vue'
import getPosts from '../composables/getPosts'

export default {
  name: 'HomeView',
  components: { PostList },
  setup() {
     
     const { posts, error, load } = getPosts()

     load()

     return { posts, error }
  }
 }
</script>
