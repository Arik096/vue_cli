<template>
  <div class="home">
    <router-link :to="{ name:'Home' }">
      <h1>Home</h1>
    </router-link>
    
    <div v-if="error">{{ error }}</div>
    <div v-if="posts.length">
      <PostList :posts="posts" />
    </div>
    <div v-else>Loading....</div>
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import getPosts from "../composables/getPosts.js";

export default {
  name: "Home",
  components: {
    PostList,
  },
  setup() {
    
    const { posts, error, load} = getPosts();
    load();

    return { posts, error };
  },
};
</script>
