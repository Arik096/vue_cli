<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="Search">
    <p>Searched Term - {{Search}}</p>
    <div v-for="name in matchName" :key="name">
      {{name}}
    </div>
  </div>
</template>

<script>
import { computed, ref } from 'vue';


export default {
  name: 'Home',
  setup(){

    const Search = ref('');
    const names = ref(['arik','puja','rafi','pavel']);

    const matchName = computed( () => {
      return names.value.filter( (name) => name.includes(Search.value));
    });

    return{ names, Search, matchName };
  },
}
</script>
