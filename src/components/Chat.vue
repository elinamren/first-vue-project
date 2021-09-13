<template>
  <div class="chat-wrapper">
    <section class="chat" id="chat">
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
    <section class="user-msg">
      <div class="bubble user-bubble">
        <p>Hej!</p>
      </div>
    </section>

    <div class="input-wrapper" id="input-wrapper">
      <form id="name-form">
        <input id="name-input" type="text" />
        <button class="send-btn" type="submit">
          Send
        </button>
      </form>
    </div>
  </div>
</template>

<style scoped>
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
  opacity: 0.9;
  transition: all 0.2s ease;
}
</style>
