<template>
  <div class="home">
    <h1>hello world</h1>
  </div>
</template>

<script>

export default {
  name: 'Home',
  setup(){
    console.log("setup");
  },
  created(){
    console.log("created");
  },
  mounted(){
    console.log("mounted");
  }
}
</script>
