<template>
  <div class="home">
    <h1>Home</h1>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";

export default {
  name: "Home",
  components: {
    PostList,
  },
  setup() {
    const posts = ref([
      { title: 'Welcome to the blog', body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi non quis exercitationem culpa nesciunt nihil aut nostrum explicabo reprehenderit optio amet ab temporibus asperiores quasi cupiditate. Voluptatum ducimus voluptates voluptas?', id: 1 },
      { title: 'Top 5 CSS Tricks', body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eligendi non quis exercitationem culpa nesciunt nihil aut nostrum explicabo reprehenderit optio amet ab temporibus asperiores quasi cupiditate. Voluptatum ducimus voluptates voluptas?', id: 2 },
    ]);

    return { posts };
  },
};
</script>
