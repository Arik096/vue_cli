<template>
  <h1>Jobs</h1>
  <div v-if="jobs.length">
    <div v-for="job in jobs" :key="job.id">
      <router-link :to="{ name: 'JobsDetails', params: { id: job.id } }">
        <h4>{{ job.title }}</h4>
      </router-link>
    </div>
  </div>
  <div v-else>
    <p>loading...</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [],
    };
  },
  mounted() {
    fetch("http://localhost:3000/jobs")
      .then((res) => res.json())
      .then((data) => (this.jobs = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style>
</style>