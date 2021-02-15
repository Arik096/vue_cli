<template>
  <div class="home">
    <h1>hello world</h1>
    <p ref="p">my name is {{name}}, my age is {{age}}</p>
    <button @click="handleclick">click me</button>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'Home',
  setup(){

    const p = ref(null);

    let name = 'mario';
    let age = 20;

    const handleclick = () => {
      console.log(p.value);
      p.value.classList.add('test');
    }

    return{ name, age, handleclick, p};
  },
  created(){},
  mounted(){}
}
</script>
