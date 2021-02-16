<template>
  <dvi class="post">
    <h3>{{ post.title }}</h3>
    <p>{{ snipet }}...</p>
  </dvi>
</template>

<script>
import { computed } from 'vue';
export default {
  props: ['post'],
  setup( props ){

      const snipet = computed ( () => {
          return props.post.body.substring(0,100);
      } );

      return { snipet };
  }
};
</script>

<style>
</style>