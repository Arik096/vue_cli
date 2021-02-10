<template>
<h3>Time: {{resultTime}}ms</h3>
<hr>
<h1>{{rank}}</h1>
</template>

<script>
export default {
props: ['resultTime'],
data(){
    return{
        rank: ""
    }
},
mounted(){
    if(this.resultTime < 400){
        this.rank = "Hero";
    }
    else if(this.resultTime < 600){
        this.rank = "good";
    }
    else{
        this.rank = "looser";
    }
    
}
}
</script>

<style>

</style>