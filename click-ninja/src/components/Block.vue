<template>
  <div class="main-block" v-if="isShow" @click="stopTimer">
      click me
  </div>
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return{
            isShow: false,
            timer: null,
            totalTime: 0,
        }
    },
    mounted() {
        setTimeout(() => {
            this.isShow = true;
            this.startTimer();
        }, this.delay);
    },
    methods: {
        startTimer(){
            this.timer = setInterval(() => {
                this.totalTime = this.totalTime + 10;
            }, 10);
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit("end", this.totalTime);
        }
    }
}
</script>

<style>
template{
    display: flex;
    justify-items: center;
}
.main-block{
    border: 1px solid red;
    background-color: aqua;
    margin:40px auto;
    width: 100px;
    height: 100px;
    text-align: center;
}
</style>