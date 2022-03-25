<template>
  <div id="app">
    <header-dischi @cambioGenere="impostaGenere"></header-dischi>
    <main-dischi :genere-selezionato="opzioneSelezionata"></main-dischi>
  </div>
</template>

<script>
import HeaderDischi from "./components/HeaderDischi.vue";
import MainDischi from "./components/MainDischi.vue";

export default {
  name: "App",
  components: {
    HeaderDischi,
    MainDischi,
  },

  data() {
    return {
      opzioneSelezionata: "",
    };
  },

  methods: {
    impostaGenere(opzioneSelezionata) {
      this.opzioneSelezionata = opzioneSelezionata;
    },
  },
};
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";
</style>
