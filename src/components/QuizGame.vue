<template>
  <div class="game">
    <div class="question">
      <div class="operand">56</div>
      <div class="operator">+</div>
      <div class="operand">34</div>
    </div>
    <keypad :onInput="onInput" :onSubmit="onSubmit" :onReset="onReset" :show="showKeypad"/>
  </div>
</template>

<script>
import keypad from "@/components/KeyPad.vue";

export default {
  name: "QuizGame",
  components: {
    keypad
  },
  data: () => ({
    number: "",
    maxLength: 6,
    showKeypad: true
  }),
  methods: {
    onInput(key) {
      this.number = (this.number + key).slice(0, this.maxLength);
    },
    onSubmit() {
      alert("Sumitted: " + this.number);
    },
    onReset() {
      this.number = "";
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.game {
  color: red;
  font-size: 16px;
}
.question {
  display: grid;
  grid-gap: 10px;
  grid-template-columns: repeat(6, 100px);
}
</style>
