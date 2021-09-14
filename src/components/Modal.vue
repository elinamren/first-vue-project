<template>
  <div class="modal">
    <h2>Chat with me!</h2>
    <Chat />
  </div>
</template>

<script>
import Chat from "./Chat.vue";

export default {
  components: { Chat },
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.modal {
  padding: 20px;
  margin: 20px auto;
  border-radius: 10px;
  background: white;
  width: 50%;
}

h2 {
  color: black;
}
</style>
