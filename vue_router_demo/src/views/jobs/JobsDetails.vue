<template >
  <div v-if="job">
    <h3>Job Details Page</h3>
    <h1>{{ job.title }}</h1>
    <h3>{{ job.id }}</h3>
    <h5>{{ job.slug }}</h5>
  </div>
  <div v-else>
      <p>loading...</p>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      //id: this.$route.params.id,
      job: null,
    };
  },
  mounted() {
    fetch("http://localhost:3000/jobs/" + this.id)
      .then((res) => res.json())
      .then((data) => (this.job = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style>
</style>