<template>
  <div class="google-maps">
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2913.208900591435!2d-0.05623088452010546!3d43.10012457914417!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xd57d421a8f95d75%3A0xa901dbed819b86a7!2s9+Avenue+Antoine+Beguere%2C+65100+Lourdes!5e0!3m2!1sfr!2sfr!4v1500813554286"
      width="600"
      height="450"
      frameborder="0"
      style="border:0"
      allowfullscreen
    ></iframe>
  </div>
</template>

<script>
import axios from "axios";
import router from "../router";

export default {
  name:"Noustrouver",
    methods: {
    getData: function() {
      axios
        .get("/api/noustrouver")
        .then(response => {
          console.log(response);
        })
        .catch(errors => console.log(errors));
    }
  },
  mounted() {
    this.getData();
  }
};
</script>

<style>
.google-maps {
  position: relative;
  padding-bottom: 40%;
  height: 0;
  overflow: hidden;
}
.google-maps iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100% !important;
  height: 100% !important;
}
</style>
