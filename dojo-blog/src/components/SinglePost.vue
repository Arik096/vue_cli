<template>
  <dvi class="post">
    <router-link :to="{ name: 'PostDetails', params: {id: post.id}}">
      <h3>{{ post.title }}</h3>
    </router-link>
    <p>{{ snipet }}...</p>
    <span v-for="tag in post.tags" :key="tag"> #{{ tag }}</span>
  </dvi>
</template>

<script>
import { computed } from "vue";
export default {
  props: ["post"],
  setup(props) {
    const snipet = computed(() => {
      return props.post.body.substring(0, 100);
    });

    return { snipet };
  },
};
</script>

<style></style>
