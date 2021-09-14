<template>
  <div class="chat-wrapper">
    <section class="chat" id="chat" ref="chat">
      <section class="bot-msg">
        <img
          src="https://image.flaticon.com/icons/png/512/1587/1587565.png"
          alt="Bot"
        />
        <div class="bubble bot-bubble">
          <p>Hej! Vad heter du?</p>
        </div>
      </section>
    </section>

    <div class="input-wrapper" id="input-wrapper">
      <form id="name-form" v-if="showForm">
        <input id="name-input" type="text" ref="input" />
        <button class="send-btn" type="submit" @click="getNameAnswer">
          Send
        </button>
      </form>
      <div class="button-wrapper" v-if="showButtons">
        <button class="send-btn" type="button" @click="pepp">
          Pepp
        </button>
        <button class="send-btn" type="button" @click="tarot">
          Tarot kort
        </button>
        <button class="send-btn" type="button" @click="weather">
          Veta vädret
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      showButtons: false,
      showForm: true,
      peppQuotes: [
        "Allt jag behöver finns inom mig.",
        "Energin du sprider ut kommer komma tillbaka till dig.",
        "Lita på att saker händer av en anledning",
        "DU kan göra det!",
        "Dröm stort.",
        "Äg din lycka, fokusera på det som gör dig glad",
      ],
      tarotkort: [
        "Månen, representerar falska beskyllningar, dolda fiender, och fara. Kortet kan i mer extrama tolkningar betyda mörker and fasa.",
        "Rättvisan, står för rättvisans triumf, lag, sanning, kontroll och kontrakt. Å andra sidan kan också kortet dyka upp då man har problem med rättvisan och när man anklagar eller blir anklagad. Vissa tarottolkare anser kortet har med beslut att göra.",
        "Vagnen, står för krig, vedergällning, hämnd och motstånd men även för skydd och triumf. Du kommer snart att ta kontrollen över situationen och gå vidare.",
        "Två i bägare, står för kärlek. Du känner stark gemenskap med en partner, vän eller kollega. Eller har det skett ett oväntat möte med någon som du finner attraktiv eller som du tycker om? Två i bägare brukar även stå för förtroliga samtal mellan två människor.",
        "Drottning i pentagram, en praktisk kvinna som man kan lita på. Hon är en riktig affärskvinna, smart och som kommer att kämpa för sin rätt. När det handlar om pengar kan den här kvinnan vara rätt så hård och envis. Som situation betyder kortet att man tänker praktiskt i materiella frågor. Drottning i Pentagram är snäll och delar med sig, men hon får inte alltid någon stöd från omgivningen, även när hon verkligen förtjänar det. Drottning i Pentagram har således en hel del gemensamt med Kejsarinnan och står även för alla kvinnliga healers. För en man kan kortet betyda att han är gift.",
      ],
    };
  },
  methods: {
    getRandom(number) {
      return Math.floor(Math.random() * number);
    },
    getNameAnswer(event) {
      event.preventDefault();
      this.showMessage(this.$refs.input.value, "user");
      this.name = this.$refs.input.value;
      this.$refs.input.value = "";
      this.showMessage(`Trevligt ${this.name}, Vad behöver du idag?`, "bot");
      this.showForm = false;
      this.showButtons = true;
    },
    showMessage(message, sender) {
      setTimeout(() => {
        const chat = this.$refs.chat;
        if (sender === "user") {
          chat.innerHTML += `
            <section class="user-msg">
                <div class="bubble user-bubble">
                    <p>${message}</p>
                </div>
            </section>
          `;
        } else {
          chat.innerHTML += `
            <section class="bot-msg">
                <img
                    src="https://image.flaticon.com/icons/png/512/1587/1587565.png"
                    alt="Bot"
                />
                <div class="bubble bot-bubble">
                    <p>${message}</p>
                </div>
            </section>
        `;
        }
        chat.scrollTop = chat.scrollHeight;
      }, 1000);
    },

    pepp() {
      this.showMessage("Pepp", "user");
      this.showMessage(
        this.peppQuotes[this.getRandom(this.peppQuotes.length)],
        "bot"
      );
    },
    tarot() {
      this.showMessage("Tarotkort", "user");
      this.showMessage(
        this.tarotkort[this.getRandom(this.tarotkort.length)],
        "bot"
      );
    },
    weather() {
      this.showMessage("Vädret just nu", "user");
      this.showMessage(`Sol och 10 grader`, "bot");
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
  text-align: left;
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
