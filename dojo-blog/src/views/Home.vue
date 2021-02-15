<template>
  <div class="home">
    <h1>hello world</h1>
    <p>my name is {{data1.name}}, my age is {{data1.age}}</p>
    <button @click="handleclick1">click me</button>
    <hr>
    <p>my name is {{data2.name}}, my age is {{data2.age}}</p>
    <button @click="handleclick2">click me</button>
  </div>
</template>

<script>
import { ref, reactive } from 'vue';

export default {
  name: 'Home',
  setup(){

    const data1 = ref({ name: 'arik', age: 25 });
    const data2 = reactive({ name: 'puja', age: 20 });



    const handleclick1 = () => {
      data1.age.value = data1.value.age++;
    }
    
    const handleclick2 = () => {
      data2.value = data2.age++;
    }

    return{handleclick1, handleclick2, data1, data2};
  },
  created(){},
  mounted(){}
}
</script>
