<template>
  <div>
    <h1>{{ title }}</h1>
    <Modal />
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
    };
  },
  methods: {},
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
  padding: 80px;
}
button {
  background-color: #00909d;
  color: white;
  border: none;
  border-radius: 4px;
  padding: 16px 40px;
  margin-right: 4px;
  font-size: 16px;
  line-height: 26px;
  cursor: pointer;
  transition: all 0.3s ease;
}

button:hover {
  opacity: 0.8;
}

.cta-button:active {
  opacity: 0;
}

.cta-button {
  margin: 20px;
}
</style>
