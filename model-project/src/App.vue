<template>
  
  <h1>{{title}}</h1>
  <Modal :header="header" :text="text" theme='dark'/>
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
      title: "my 1st app",
      header: "Signup for giveway!",
      text: "hello"
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
  color: #c21f1f;
  margin-top: 60px;
  border: 2px solid rgb(255, 252, 252);
}
</style>
