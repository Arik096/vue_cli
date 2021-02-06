<template>
  
  <h1>{{title}}</h1>
  <button @click="toggleModal"> open modal 1</button>
  <button @click="toggleModal2"> open modal 2</button>
  <teleport to="#modals" v-if="showModal">
    <Modal theme='sale' @close="toggleModal">
      <h1>Title</h1>
      <p>Arik Md Isthiaque</p>
      <template v-slot:links>
        <a href="#">sign up</a>
        <a href="#">log in</a>
      </template>
      </Modal>
  </teleport>
  <teleport to="#modals" v-if="showModal2">
    <Modal theme='drak' @close="toggleModal2">
      <h1>Title</h1>
      <p>Pritilata Biswas</p>
      <template v-slot:url>
        <a href="#">sign up</a>
        <a href="#">log in</a>
      </template>
    </Modal>
  </teleport>
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
      text: "hello",
      showModal: false,
      showModal2: false
    }
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal;
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2;
    },
  }
}
</script>

<style>
#app, #modals{
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
  margin-top: 10px;
}
</style>
