<template>
  <h3>Job Details Page</h3>
  <p><strong>{{ id }}</strong></p>
</template>

<script>
export default {
    data(){
        return{
            id: this.$route.params.id,
        }
    }
}
</script>

<style>

</style>