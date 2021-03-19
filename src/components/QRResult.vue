<template>
  <div>
    <h2>Here's your result!</h2>
    <canvas ref="canvas" />
    <button @click="download">Download</button>
  </div>
</template>

<script>
const QRCode = require("qrcode");
const saveAs = require("file-saver");

export default {
  name: "QRResult",
  props: ["qrData"],
  watch: {
    qrData(newData) {
      QRCode.toCanvas(this.$refs.canvas, newData, { width: 500 });
    },
  },
  methods: {
    download() {
      this.$refs.canvas.toBlob((blob) => {
        saveAs(blob, "qr.png");
      });
    },
  },
};
</script>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
