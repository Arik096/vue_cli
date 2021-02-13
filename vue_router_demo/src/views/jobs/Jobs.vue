<template>
  <h1>Jobs</h1>
  <div v-for="job in jobs" :key="job.id">
      <router-link :to="{name: 'JobsDetails', params: {id: job.id} }">
          <h4>{{job.title}}</h4>
      </router-link>
  </div>
</template>

<script>
export default {
    data(){
        return{
            jobs: [
                {title: 'ux', id: 1, slug: 'lorem'},
                {title: 'web', id: 2, slug: 'lorem'},
                {title: 'android', id: 3, slug: 'lorem'},
            ]
        }
    }
}
</script>

<style>

</style>