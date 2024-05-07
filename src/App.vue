<template>
  <div>
    <h1 :class="{ 'red-text': isRed }">Dynamic Interaction with Vue</h1>
    <p :style="{ fontSize: fontSize + 'px' }">Change font size:</p>
    <input type="range" min="10" max="50" v-model="fontSize">
    <br>
    <input type="text" v-model="inputText" @input="updateText">
    <p>You typed: {{ inputText }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fontSize: 16,
      inputText: '',
      isRed: false
    };
  },
  methods: {
    updateText() {
      this.isRed = this.inputText.length > 10;
    }
  }
}
</script>

<style scoped>
.red-text {
  color: red;
}
</style>
