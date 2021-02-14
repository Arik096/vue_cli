<template>
  <div class="home">
    <h1>hello world</h1>
    <p>my name is {{name}}, my age is {{age}}</p>
    <button @click="handleclick">click me</button>
  </div>
</template>

<script>

export default {
  name: 'Home',
  setup(){
    console.log("setup");

    let name = 'mario';
    let age = 20;

    const handleclick = () => {
      console.log("clicked");
    }

    return{ name, age, handleclick};
  },
  created(){
    //console.log("created");
  },
  mounted(){
    //console.log("mounted");
  }
}
</script>
