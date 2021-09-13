<template>
  <div>
    <h1>{{ title }}</h1>
    <Modal v-if="showModal" @close="handleClick" />
    <button @click="handleClick">Talk to the bot</button>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first Vue project",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      this.showModal = !this.showModal;
    },
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
  height: 100vh;
  padding: 50px;
}
</style>
