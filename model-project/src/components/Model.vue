<template>
    <div class="dropout" @click="closeModal()">
        <div class="modal" :class="{sale: theme === 'sale', dark: theme === 'dark'}">
            <h1>modal</h1>
            <h1>{{header}}</h1>
            <p>modal content</p>
            <strong>{{text}}</strong>
        </div>
    </div>
</template>

<script>
export default {
    props: ["header", "text" , "theme"],
    methods: {
        closeModal(){
            this.$emit('close');
        }
    }
}
</script>

<style>
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: rgb(50, 134, 113);
    border-radius: 10px;
}
.backdrop{
    top: 0;
    position: absolute;
    z-index: 0;
    background: rgba(155, 67, 67, 0.5);
    width: 100%;
    height: 100%;
}
.modal h1{
    color:aliceblue;   
}
.modal p{
    font-style: normal;
}
.modal.sale{
    background-color: crimson;
    color: white;
}
.modal.dark{
    background-color: darkslateblue;
    color: wheat;
}
</style>