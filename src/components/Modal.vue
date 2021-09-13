<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal">
      <h2>Chat with me!</h2>
      <Chat />
    </div>
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
  margin: 10% auto;
  border-radius: 10px;
  background: white;
  width: 50%;
}
.backdrop {
  top: 0;
  left: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}

h2 {
  color: black;
}
</style>
