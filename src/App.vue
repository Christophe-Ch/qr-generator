<template>
  <div id="app">
    <h1>QR Generator</h1>
    <QRForm @dataReady="getData" />
    <QRResult :qrData="qrData" v-show="qrData != null" />
  </div>
</template>

<script>
import QRForm from "./components/QRForm.vue";
import QRResult from "./components/QRResult.vue";

export default {
  name: "App",
  components: {
    QRForm,
    QRResult,
  },
  data() {
    return {
      qrData: null,
    };
  },
  methods: {
    getData(newData) {
      this.qrData = newData;
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
  margin-top: 60px;
}
</style>
