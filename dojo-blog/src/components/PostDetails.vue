<template>
<router-link :to="{ name:'Home' }">
      <h1>Home</h1>
    </router-link>
  <div v-if="error">{{error}}</div>
  <div v-if="post" class="post"> 
      <h1>{{post.title}}</h1>
      <br>
      <hr>
      <br>
      <h5>{{post.body}}</h5>
      <span v-for="tag in post.tags" :key="tag">
          <p>#{{tag}}</p>
      </span>
      
  </div>
</template>

<script>
import getPost from "../composables/getPost.js"

export default {
props: [ 'id'],
setup(props){
    const { post, error, load} = getPost(props.id);
    

    load();

    return { post, error }
}
}
</script>

<style>

</style>