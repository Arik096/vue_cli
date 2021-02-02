<template>
  
  <h1>{{title}}</h1>
  <Modal/>
</template>

<script>
import Modal from './components/Model.vue';

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      title: "my 1st app"
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  border: 2px solid black;
}
</style>
