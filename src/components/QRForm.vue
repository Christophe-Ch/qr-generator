<template>
  <div>
    <h2>Alright, what do you want to encode?</h2>
    <input type="text" v-model="qrData" />
    <button @click="sendData">Encode</button>
  </div>
</template>

<script>
export default {
  name: "QRForm",
  data() {
    return {
      qrData: null,
    };
  },
  methods: {
    sendData() {
      this.$emit("dataReady", this.qrData);
    },
  },
};
</script>

<style>
h1 {
  font-size: 3em;
}
input,
button {
  padding: 5px;
  margin: 0 5px;
}
</style>
