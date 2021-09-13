<template>
  <div class="chat-wrapper">
    <section class="chat" id="chat" ref="chat">
      <section class="bot-msg">
        <img
          src="https://image.flaticon.com/icons/png/512/1587/1587565.png"
          alt="Bot"
        />
        <div class="bubble bot-bubble">
          <p>Hej!</p>
        </div>
      </section>
    </section>

    <div class="input-wrapper" id="input-wrapper">
      <form id="name-form">
        <input id="name-input" type="text" ref="input" />
        <button class="send-btn" type="submit" @click="showMessage">
          Send
        </button>
      </form>
    </div>
  </div>
</template>

<script>
import UserMessage from "./UserMessage.vue";

export default {
  components: { UserMessage },
  methods: {
    showMessage(event) {
      event.preventDefault();
      this.$refs.chat.innerHTML += `
        <section class="user-msg">
    <div class="bubble user-bubble">
      <p>${this.$refs.input.value}</p>
    </div>
  </section>
      `;
      this.$refs.input.value = "";
    },
  },
};
</script>

<style>
input {
  box-sizing: border-box;
  border: none;
  border-radius: 4px 0 0 4px;
  background: #c8e4e7;
  color: #015081;
  padding: 16px;
  font-size: 16px;
  line-height: 26px;
  flex: 1;
}

.chat-wrapper {
  margin: 0 auto;
  width: 100%;
  max-width: 700px;
  height: 600px;
  border-radius: 30px;
  background: #fff;
  padding: 20px 24px;
  padding-top: 0;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
}

.chat {
  flex: 1;
  display: flex;
  justify-content: flex-start;
  overflow-y: scroll;
  flex-direction: column;
  padding-bottom: 16px;
}

.bot-msg {
  display: flex;
  margin: 16px 8px 0 0;
  flex-shrink: 0;
}

.user-msg {
  display: flex;
  justify-content: flex-end;
  margin: 16px 0 0 8px;
  flex-shrink: 0;
}

.bot-msg img,
.user-msg img {
  width: 60px;
  height: 60px;
}

.bubble {
  font-weight: 600;
  font-size: 16px;
  line-height: 26px;
  padding: 16px 24px;
  color: #015081;
  max-width: 40%;
}

.bot-bubble {
  border-radius: 0px 26px 26px 26px;
  margin-left: 8px;
  background: #c8e4e7;
}

.user-bubble {
  border-radius: 26px 0 26px 26px;
  margin-right: 8px;
  background: #6ac9d2;
}

.input-wrapper {
  display: flex;
  justify-content: center;
  margin-top: 10px;
}

.input-wrapper form {
  width: 100%;
  display: flex;
}
</style>
