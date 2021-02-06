<template>
  <div class="dropout">
    <div
      class="modal"
      :class="{ sale: theme === 'sale', dark: theme === 'dark' }"
    >
      <slot>Defalut Content</slot>
      <div class="actions">
        <slot name="links"> </slot>
        <slot name="url"> </slot>
      </div>
      <br />
      <button @click.self="closeModal">close</button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: rgb(50, 134, 113);
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: absolute;
  z-index: 0;
  background: rgba(155, 67, 67, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: aliceblue;
}
.modal p {
  font-style: normal;
}
.modal.sale {
  background-color: crimson;
  color: white;
}
.modal.dark {
  background-color: darkslateblue;
  color: wheat;
}
.modal .actions a {
  color: black;
  padding: 8px;
  border: 1px solid rgb(112, 148, 112);
  border-radius: 5px;
  margin: 10px;
  text-decoration: none;
  color: wheat;
}
</style>
