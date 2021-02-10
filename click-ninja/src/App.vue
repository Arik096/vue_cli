<template>
  <h1>CLick Ninja</h1>
  <button @click="playNow" :disabled="isPlaying">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="getResultTime" />
  <Result v-if="resultTime != 0" :resultTime="resultTime" />
</template>

<script>
import Block from "./components/Block.vue";
import Result from "./components/Result.vue";

export default {
  name: 'App',
  components: { Block, Result },
  data() {
    return {
      isPlaying: false,
      delay: null,
      resultTime: 0,
    };
  },
  methods: {
    playNow() {
      this.isPlaying = true;
      this.delay = 100 + Math.random() * 500;
      this.resultTime = 0;
    },
    getResultTime(endTime){
      this.resultTime = endTime;
      this.isPlaying = false;
    }
  },
};
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
</style>
