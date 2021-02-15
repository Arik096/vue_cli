<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="Search">
    <p>Searched Term - {{Search}}</p>
    <div v-for="name in matchName" :key="name">
      {{name}}
    </div>
    <button @click="handlewatch">stop watch</button>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from 'vue';


export default {
  name: 'Home',
  setup(){

    const Search = ref('');
    const names = ref(['arik','puja','rafi','pavel']);

    const stopwatch = watch( Search, () => {
      console.log("run");
    } );

    const stopEffectwatch = watchEffect(  () => {
      console.log("done", Search.value)
    });

    const matchName = computed( () => {
      return names.value.filter( (name) => name.includes(Search.value));
    });

    const handlewatch = () => {
      stopwatch();
      stopEffectwatch();
    }

    return{ names, Search, matchName, handlewatch };
  },
}
</script>
